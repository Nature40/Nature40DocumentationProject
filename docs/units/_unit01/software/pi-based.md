---
title: Raspberry Pi-based Sensorboxes
toc: true
toc_label: Content
header:
  image: /assets/images/01-splash.jpg
  image_description: "Image Panel Natur 4.0 Sensorboxes"
  caption: "Images Natur4.0 / CC0"
---

The heart of these Sensorboxes is [pysensorproxy](https://github.com/Nature40/pysensorproxy) used to schedule, execute and transmit environmental measurements. 
For the Raspberry Pi (RPi) based Sensorboxes the default [Raspbian Operating System](http://www.raspbian.org) is used. 
Our software, as well as other features, such as mesh networking, remote access via ssh or hardware used in the boxes require further installation of software and configuration.
In the first stage common configuration files and custom software are installed using [pimod](https://github.com/Nature40/pimod/), which allows to reconfigure Raspberry Pi images with an easy, Docker-like configuration file. 
In the second stage an image is flashed to an SD card and then provisioned for as specific Sensorbox using a templating engine.

![Overview of Raspberry-Pi Software and Configuration]({{site.url}}{{site.baseurl}}/assets/img/software/PiBased-Overview.svg)

## pysensorproxy

[Pysensorproxy](https://github.com/Nature40/pysensorproxy) is a python tool used to schedule, execute and transmit environmental measurements. 
It is currently targeted to be used with a Raspberry Pi, but will be extended for other sensors an platforms in the future.
Pysensorproxy is modularized by supporting various sensors configurable in a yml file.

```yaml
storage_path: /data               # path to save files

sensors:                          # list of sensors
  am2302:                           # name (choose freely)
    type: AM2302                      # type (must be in sensorproxy.sensors.*)
    pin: 4                            # additional configuration parameter
  cam:
    type: PiCamera
    img_format: jpeg
```

The meterings are done according to a configurable schedule.

```yaml
daytime:              # name of the measuring cycle
  sensors:              # dict of the sensors to be measured
    cam:                  # reference to `cam`, configured in the static config (yml)
      res_X: 3280           # image resolution, set according to https://www.raspberrypi.org/documentation/raspbian/applications/camera.md
      res_Y: 2464
      adjust_time: 2s       # time to adjust to brightness
  schedule:               # schedule parametes
    interval: 30m           # measurement is mandatory (max. 24h)
    start: 06h              # optional, according to local time
    end: 22h                # optional, according to local time
```


## Stage 1: Image Creation

The goal of the image creation stage is to reproducibly build images for Sensorboxes.
To reach this goal, common configuration files, as well as Pifiles (used by [pimod](https://github.com/Nature40/pimod/)) to install custom software are defined in [Sensorboxes-Images](https://github.com/Nature40/Sensorboxes-Images).
The defined images can be build locally, as described in the Readme, or are build and uploaded to GitHub releases using Travis-CI when git tags are pushed to the GitHub repo. 
The image creation itself happens in different layers, which has the advantage of faster build times.

#### 1. [Base](https://github.com/Nature40/Sensorboxes-Images/blob/master/Base.Pifile)

In the base image, common software and configurations for all Sensorbox types are installed:
- Default password (natur) is set
- serial interfaces is enabled
- ssh is configured and enabled
- timezone is set to Europe/Berlin
- installation: wireguard, [uhubctl](https://github.com/mvp/uhubctl)
- automated hostname configuration is added
- RTL8822BU drivers

#### 2. [Mesh](https://github.com/Nature40/Sensorboxes-Images/blob/master/Mesh.Pifile) 

Software and configuration for a B.A.T.M.A.N-based mesh, featuring IPv4 auto-configuration using the Raspberry PI serial number. 

#### 3. [Sensorbox](https://github.com/Nature40/Sensorboxes-Images/blob/master/Sensorbox.Pifile)

This layer targets the hardware and software configuration of the actual Sensorboxes (planets and moons), as described in [SensorModules](/Sensorboxes-Documentation/pages/SensorModules/SensorModules).
Currently it consists of:
- Enabling hardware: RPi camera, I2C bus, DS3231 real-time clock
- installation: hostapd, dnsmasq, pysensorproxy

## Stage 2: Sensorbox provisioning

All common software and configuration for the Sensorboxes is done in stage 1.
As some configuration aspects of the Sensorboxes differ from appliance to appliance, these need to be configured per Sensorbox. 
Also some configuration aspects might need to be private, as passwords. 
[Sensorboxes-Config](https://github.com/Nature40/Sensorboxes-Config) holds Sensorbox-specific configurations, as well as private information, and thus is not publicly available. 

#### [generate_config.py](https://github.com/Nature40/Sensorboxes-Config/blob/master/generate_config.py)

Simple, yet powerful [jinja2]()-based templating for configuration files. 
It takes one generic input file and a yml file, containing variables in key-value format.
 
#### [_deployments](https://github.com/Nature40/Sensorboxes-Config/tree/master/_deployments)
The folder contains a yml for each individual Sensorbox installation. 
The variables defined in the yml are used in the templating engine

```yml
deployment: mof_cst_00008
planet: nature40-sensorbox-9a3fcc8c
moon: nature40-sensorbox-
liftsystem: nature40-liftsystem-
height: 0
gps: [0.0, 0.0]
tel: ""
```

#### Configuration folders, e.g.[default/planet](https://github.com/Nature40/Sensorboxes-Config/tree/master/default/planet)

All the files inside a configuration folders are processed using [generate_config.py](https://github.com/Nature40/Sensorboxes-Config/blob/master/generate_config.py) and copied into the boot partion of the flashed image.

```yml
{% raw %}
id: {{ deployment }}_planet
storage_path: /data
{% endraw %}
```

In this example `{% raw %}{{ deployment }}{% endraw %}` will be replaced by the value defined in the deployment file, respectively.

#### Usage

##### `flash.sh`: Flash an image to a device
```
usage: ./flash.sh <SOURCE_IMG> <DEST_DEV>
```

##### `configure.sh`: Write configuration filled accordingly to a deployment.
```
usage: ./configure.sh <DEST_DEV> <TEMPLATE_PATH> <DEPLOYMENT>
```

##### `provision.sh`: Provision (flash and configure) an SD card.
```
usage: ./provision.sh <SOURCE_IMG> <DEST_DEV> <TEMPLATE_PATH> <DEPLOYMENT>
```

##### `remote.sh`: Write configuration filled accordingly to a deployment via ssh.
```
usage: ./remote.sh <TEMPLATE_PATH> <DEPLOYMENT> <SSH_HOST>
```

##### `wireguard.sh`: Print wireguard configuration and append to ssh/wireguard config.
```
usage: ./wireguard.sh <DEPLOYMENT>
```

##### `wireguard-full.sh`: Recreate wireguard configuration for all deployments
```
usage: ./wireguard-full.sh
```


