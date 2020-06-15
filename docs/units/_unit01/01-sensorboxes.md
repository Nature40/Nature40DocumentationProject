---
title: Nature 4.0 Sensor Boxes
toc: true
toc_label: Content
header:
  image: /assets/images/01-splash.jpg
  image_description: "Image panel Natur 4.0 sensor boxes"
  caption: "Images Natur4.0 / CC0"
---



Description of sensors and sensor boxes designed and used in the Nature 4.0 project. The sensor systems encompass multiple different box types and use cases.
<!--more-->
This section documents the hardware, software and deployment of our stations. Stations are named as follows:
* [Power Supply](00_power_supply): containment, solar charger, connectors
* [Planet](01_planet): Static unit with networking and storage capabilities
* [Moon](02_moon): Vertically moving unit
* [GW1000 Hub](03_gw1000): Static sensorbox fpr climate mesurements and data retrieval
* [Lift Engine](04_liftengine): Wooden box holding a motor
* [Lift Controller](05_liftcontroller): Helper unit, controlling the motor

## Planets and Moons

We refer to *planets* and *moons* for sensor boxes with higher processing capabilities fulfilling infrastructural tasks. A planet explicitly has the task to collect data over longer time periods, while a moon can process data, but has to offload its data quite frequently.

## Satellites and Probes

*Satellites* and *probes* are devices fulfilling one specific task. This allows them to take advantages from deep-sleep capabilities of modern devices. While they can work independently by writing their data e.g. onto an SD card, they are built to make use of the communication and storage infrastructure offered by our planets and moons. A satellite is bound to a planet or moon, while a probe works independently from one.

## Sensorbox
The figure below shows a moon sensorbox, which is able to vertically move up along a tree in order to record microclimate, bird songs and canopy images at different heights.
{% include figure image_path="/assets/images/insideBox.jpg" alt="Example Moon Sensorbox" %}
The sensorbox contains a Raspberry Pi single-board-computer which records the connected sensors consisting of a camera, a microphone, temperature & humidity and a lux sensor. It is powered by a generic powerbank, which itself is charged through a QI charging pad, when at the bottom of the station.

## Software
The sensor boxes used in this project are based on two different platforms:
1. [Raspberry Pi-based Sensorboxes]({{site.url}}{{site.baseurl}}/pages/Software/PiBased/) for date-intensive applications, such as photos or videos.
2. Arduino-based boxes for easier tasks and sensors, such as temperature or humidity.

## Additional sources
Our project works with Commodity-Off-the-Shelf (COTS) hardware wherever possible. Custom made and 3D-printed parts are described in the [Sensorboxes-Design repository] (https://github.com/Nature40/Sensorboxes-Design). Software for recording sensor data is available through the [Pysensorproxy repository](https://github.com/Nature40/pysensorproxy) and Raspberry Pi images can be configured with helpers from the [Pimod repository](https://github.com/Nature40/pimod).
