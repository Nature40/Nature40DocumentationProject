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

Currently 6 Wifi Hubs with 8 sensors and one base station each are connected  via via LoRa radio. The base station is equipped with wind vector, precipitation irradiance and temperature/humidity sensors. The Wifi Hub in turn uses any accessible WLAN to pass on the data in this case via mobile network to a data server.  

## Sensor Specification 

### DP1500 WiFi hub:
* Frequency: 868Mhz
* Transmission power: 15.06dBm
* Temperature range: -10°C to +60°C, resolution: 0.1°C, accuracy: +/- 1°C
* Air humidity range: 10% - 99%, Resolution: 1%, accuracy: +/- 5%.
* Air pressure range: 300-1100hPa, resolution: 0.1 hPa, accuracy: +/- 5hPa
* Power supply: USB 5V

### DP50 temperature/humidity sensor:
* Frequency: 868Mhz
* Transmission power: -6.44dBm
* Temperature range: -10°C to +60°C, resolution: 0.1.°C, accuracy: +/- 1°C
* Air humidity range: 10% - 99%, resolution: 1%, accuracy: +/- 5%.
* Transmission interval: 48 seconds
* Power supply: 2 x 1.5V AA batteries
  
### Base Unit:
* Transmission distance in open field: 100m
* Frequency: 868Mhz
* Temperature range: -40°C to +60°C, accuracy: +/- 1°C
* Measuring range rel. humidity: 10% - 99%, accuracy: +/- 5%
* Precipitation: 0-9999mm, resolution  +/- 0.25mm, accuracy: +/- 10%
* Wind speed: 0-50m/s, accuracy: +/- 3.5 km/h or 10%
* Wind speed/gust calculation every 16 s
* Wind direction accuracy: +/- 1°
* UVI - Range: 0 - 15 index, UV accuracy: +/- 15%
* Light: 0 - 200k Lux, Solar radiation accuracy +/- 15%
* Measuring interval outdoor unit: 16 seconds
* Power supply:  Outdoor unit: 2 x 1.5V batteries The primary energy source is the solar panel. The batteries provide backup power when solar energy is limited.


## Channel Assignment and and Station Coding

|HubId          |WeatherStationId                |BaseID|CH01|CH02|CH03|CH04|CH05|CH06|CH07|CH08|SoilCh1|SoilCh2|
|---------------|--------------------------------|------|----|----|----|----|----|----|----|----|-------|-------|
|GW100A-WIFI23C6|82EB09C99462A1AE B32109AFC514F264|78    |f3  |b8  |    |4   |    |    |    |93  |c692   |c825   |
|GW100A-WIFI243E|E5C37C83C2C1EB2C 62BC8FC299D8E281|45    |e0  |b8  |49  |c8  |42  |eb  |20  |bc  |       |       |
|GW100A-WIFIF774|D3E7B46BC773DA5D 0D30F7B94570700F|cc    |40  |b8  |22  |bb  |d   |db  |5b  |65  |       |       |
|GW100A-WIFIF824|64B95BE38E36DB75 ECE69E193C9CFD62|2f    |33  |ee  |2d  |c0  |fd  |f1  |6e  |7a  |       |       |
|GW100A-WIFIFB27|C90B7356EFDA99C5 584B057DA2363EDB|3e    |3b  |b8  |e2  |4d  |89  |d2  |c3  |d3  |       |       |
|GW100A-WIFIFC29|CC354E3266838432 3E5CB75B8D4A4722|7c    |f   |b8  |92  |9c  |c   |57  |53  |9d  |       |       |

## Calibration Concept

The low budget Sensors are usually lacking of a stable measurment quality. To obtain reliable microclimate data a three step calibration process is implemented. In a first step the measurements of all sensors will be statistically analysed to identfy sensor wich produce outliers. In a second step the sensors will be calibrated in controlled climate settings (-15!C , 15°C and 45°C). Finally the sensors are calibrated against an operational running high price reference station in the field. 
For the future a machine learning approach including the radiation, azimuth, temperature and humidity as predictors for the calibrated temperature as the response variable will be used as an rolling calibration tool. 

### First Calibration Period

The first calibration step is completed. 


{% include gallery id="panel1"  caption= "*Calibration setup. Unprotected Sensors (left), Setup of a radiation shield (middle), all sensor protected with a passive radiation shield (right)*" layout ="third"  %}
The 40+ sensors will be moved to the Campbell reference station in the Marburg Open Forest at the beginning of week 24, where calibration phase 2 will start.