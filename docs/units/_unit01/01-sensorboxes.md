---
title: Nature 4.0 Sensorboxes - Overview
toc: true
toc_label: Content
header:
  image: /assets/images/01-splash.jpg
  image_description: "Image Panel Natur 4.0 Sensorboxes"
  caption: "Images Natur4.0 / CC0"
---



On this page the Sensorboxes created in the Nature 4.0 project are described and documented. Our sensor system consists of multiple different box types, matching different use cases. 

This page documents the [hardware construction](hardware), [software aspects](software) as well as the [actual deployment](liftengine#deployment-of-the-base-station) of a station.

We follow a classification defined in the project:

The sensorboxes system is based upon homogeneous hardware components. This helps to get experienced with the components, and allows to get faster in construction.

In the current state, the sensor system consists of the following integrated boxes:

* [Power Supply](power_supply): containment, solar charger, connectors
* [Planet](planet): Static unit with networking and storage capabilities 
* [Moon](moon): Vertically moving unit
* [Lift Engine](liftengine): Wooden box holding a motor
* [Lift Controller](liftcontroller): Helper unit, controlling the motor


### Planets & Moons

We refer to Planets and Moons for sensorboxes with higher processing capabilities, which, e.g., fulfill infrastructural tasks. A planet explicitly has the task to collect data for longer periods of time, while a moon can process data, but is intendet to offload its data quite frequently. 

### Satellites & Probes

Satellites and Probes are devices fulfilling one specific task, which allows them to have advantages by using deep-sleep capabilities of modern devices. While they can work independently by writing their data e.g. onto an SD card, they are built to make use of the infrastucture offered by our planets and moons. A satellite is bound to a Planet or Moon, while a Probe works independently from one.

## A Sensorbox

The figure below shows a Moon Sensorbox, which is able to be moved along a tree, to record microclimate, bird songs and canope images on different heights. 

{% include figure image_path="/assets/images/insideBox.jpg" alt="Example Moon Sensorbox" %}

The Sensorbox contains a Raspberry Pi Single-Board-Computer which records the connected sensors consisting of a camera, a microphone, temperature & humidity and a lux sensor. It is powered by a generic powerbank, which itself is charged through a QI charging pad, when at the boottom of the station.

## Software

The Sensorboxes used in this project are based on two different platforms:

1. [Raspberry Pi-based Sensorboxes]({{site.url}}{{site.baseurl}}/pages/Software/PiBased/) for date-intensive applications, such as photos or videos, and
2. Arduino-based boxes for easier tasks and sensors, such as temperature or humidity.

## Open Source

Our project works with Commodity-Off-the-Shelf (COTS) hardware for whereever possible, however there are some custom made and 3D-printed parts, which are [available at GitHub](https://github.com/Nature40/Sensorboxes-Design).

[Pysensorproxy](https://github.com/Nature40/pysensorproxy), used to record sensor meterings, as well as [Pimod](https://github.com/Nature40/pimod), implemented to create and configure Raspberry Pi images, is available Open Source and under a permissive license on GitHub. 