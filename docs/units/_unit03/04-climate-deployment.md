---
title: Climate Stations Deployment
toc: true
toc_label: Content
header:
  image: /assets/images/03-splash.jpg
  image_description: "Marburg University Forest - Central Area"
  caption: "3D Pointcloud: M. Ludwig / CC0"
  
  
panel1:
  - url: /assets/images/calib_1_1.jpg
    image_path: /assets/images/calib_1_1.jpg
    alt: "Calibration Step 1a"
  - url: /assets/images/calib_1_2.jpg
    image_path: /assets/images/calib_1_2.jpg
    alt: "Calibration Step 1b"
  - url: /assets/images/calib_1_3.jpg
    image_path: /assets/images/calib_1_3.jpg
    alt: "Calibration Step 1c"   
---


The currently used sensors are from Fine Offset Electronics and in Natur 40 identical in construction from froggit as the so-called DP series and from ecowitt with the original series identification GW-1000.<!--more-->

At the moment eight temperature/humidity sensors and a climate base station with wind vector, precipitation irradiance and temperature/humidity are linked to the WiFi Hub via proper LoRa. The Wifi Hub in turn uses any accessible WLAN to pass on the data to a server via network.  

## Sensor Specification 

### DP1500 WiFi hub:
* Frequency: 868Mhz
* Transmission power: 15.06dBm
* Temperature Measuring range: -10°C to +60°C (14°F - 140°F)
* Temperature Resolution: 0.1°C, 0.1°F
* Temperature accuracy: +/- 1°C
* Air humidity Measuring range: 10% - 99%
* Humidity Resolution: 1%.
* Air humidity Measuring accuracy: +/- 5%.
* Air pressure Measuring range: 300-1100hPa (8.85 - 32.5 inHg)
* Air pressure accuracy: +/- 5hPa
* Air pressure Resolution: 0.1 hPa (0.01 inHg)
* Power supply: USB 5V

### DP50 temperature/humidity sensor:
* Frequency: 868Mhz
* Transmission power: -6.44dBm
* Temperature Measuring range: -10°C to +60°C (14°F to 140°F)
* Temperature Resolution: 0.1.°C / 0.1°F
* Temperature accuracy: +/- 1°C
* Air humidity Measuring range: 10% - 99%
* Humidity Resolution: 1%.
* Air humidity Accuracy: +/- 5%.
* Transmission interval: 48 seconds
* Power supply: 2 x 1.5V AA batteries
  
### Base Unit:
* Transmission distance in open field: 100m
* Frequency: 868Mhz
* Temperature range: -40°C to +60°C
* Measuring range rel. humidity: 10% - 99%
* Precipitation: 0-9999mm
* Wind speed: 0-50m/s
* UVI - Range: 0 - 15 index
* Light: 0 - 200k Lux
* Measuring interval outdoor unit: 16 seconds
* Power supply:  Outdoor unit: 2 x 1.5V batteries The primary energy source is the solar panel. The batteries provide backup power when solar energy is limited.


## Calibration Concept

The low budget Sensors are usually lacking of a stable measurment quality. To obtain reliable microclimate data a three step calibration process is implemented. In a first step the measurements of all sensors will be statistically analysed to identfy sensor wich produce outliers. In a second step the sensors will be calibrated in controlled climate settings (-15!C , 15°C and 45°C). Finally the sensors are calibrated against an operational running high price reference station in the field. 
For the future a machine learning approach including the radiation, azimuth, temperature and humidity as predictors for the calibrated temperature as the response variable will be used as an rolling calibration tool. 

### First Calibration Period

The first calibration step is completed. 


{% include gallery id="panel1"  caption= "*Calibration setup. Unprotected Sensors (left), Setup of a radiation shield (middle), all sensor protected with a passive radiation shield (right)*" layout ="third"  %}
The 40+ sensors will be moved to the Campbell reference station in the Marburg Open Forest at the beginning of week 24, where calibration phase 2 will start.