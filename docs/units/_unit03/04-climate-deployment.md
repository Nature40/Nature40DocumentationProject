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

At the moment eight temperature/humidity sensors and a climate base station with wind vector, precipitation irradiance and temperature/humidity are linked to the WiFi Hub via proper LoRa. The Wifi Hub in turn uses any accessible WLAN to pass on the data to a server via _network.  

## Calibration Concept

The low budget Sensors are usually lacking of a stable measurment quality and interval. To obtain reliable microclimate data a three step calibration process is implemented. In a first step will the measurements of all sensors will be statitically analysed to identfy sensor wich produce outliers. In a second step it will be calibrated against a refernce station inthe field and in a third step a machine learning approach including the radiation azimuth temperature and humidity as predictors for the calibrated temperature as the response variable will be implemented. 

### First Calibration Period

The first calibration step is completed. 


{% include gallery id="panel1"  caption= "*Calibration setup. Unprotected Sensors (left), Setup of a radiation shield (middle), all sensor protected with a passive radiation shield (right)*" layout ="third"  %}
The 40+ sensors will be moved to the Campbell reference station in the Marburg Open Forest at the beginning of week 24, where calibration phase 2 will start.