---
title: Sensorbox Type - Lift-Sensorbox
toc: true
toc_label: Content
header:
  image: /assets/images/01-splash.jpg
  image_description: "Image Panel Natur 4.0 Sensorboxes"
  caption: "Images Natur4.0 / CC0"

panel1:
  - url: /assets/images/planet/mic_umbrella1.JPG
    image_path: /assets/images/planet/mic_umbrella1.JPG
    alt: "Construction Step 1a"
  - url: /assets/images/planet/mic_umbrella2.JPG
    image_path: /assets/images/planet/mic_umbrella2.JPG
    alt: "Construction Step 1b"
  - url: /assets/images/planet/mic_umbrella3.JPG
    image_path: /assets/images/planet/mic_umbrella3.JPG
    alt: "Construction Step 1c"  

panel2:
  - url: /assets/images/planet/mic_umbrella4.JPG
    image_path: /assets/images/planet/mic_umbrella4.JPG
    alt: "Construction Step 1d"
  - url: /assets/images/planet/mic_umbrella5.JPG
    image_path: /assets/images/planet/mic_umbrella5.JPG
    alt: "Construction Step 1e"


panel3:
  - url: /assets/images/planet/mic_cloth_1.jpg
    image_path: /assets/images/planet/mic_cloth_1.jpg
    alt: "Attaching the microphone cloth Step 1a"
  - url: /assets/images/planet/mic_cloth_2.jpg
    image_path: /assets/images/planet/mic_cloth_2.jpg
    alt: "Attaching the microphone cloth Step 1b"
  - url: /assets/images/planet/mic_cloth_3.jpg
    image_path: /assets/images/planet/mic_cloth_3.jpg
    alt: "Attaching the microphone cloth Step 1c"  

---


Building a Planet sensorbox from the type *Lift-Sensorbox* (formerly known as moon)  will be described in individual steps in this document. 

### Box and Hinges

The Spelsberg TK PC Box has the ingress protection IP66 - acc. EN 60529 / DIN VDE 0470-1 and an ambient temperature from -35 °C min. to 80 °C max. Due to it's UV resistancy, weatherproof and a rated insulation voltage 690V AC the box is fitting for outdoor application. 

{% include figure image_path="/assets/images/planet/hingeset.png" alt="Hingeset" caption="*The hingeset is added by using the supplied template*" %}


### Drilling Holes 


{% include figure image_path="/assets/images/moon/tower_template.png" alt="tower template" caption="*Then drill the holes for the sensors on the top of the containment box with the tower template*" %}

{% include figure image_path="/assets/images/moon/roll_template.png" alt="roll template" caption="*Further drill the holes with 3,5 mm drill for the rolls on both sides using the roll template*" %}

{% include figure image_path="/assets/images/moon/box_positions.png" alt="hole positions" caption="*Drill the holes for the suspension cable with 4mm drill at minimum. Insert the rope in both holes and and fix the ropes with glue. The rope should be at least 80 cm long outside the containment box.  Make sure the glue seals off the drill holes completely*" %}


### Rolls

{% include figure image_path="/assets/images/moon/rolls.png" alt="rolls" caption="*Use the six M4x16 raised countersunk-head screws with washers from inside the containment box to attach the six rolls and secure them with the six safety nuts from outside. Use instant glue under the washers and safety nuts and finally tighten the screws and nuts to ensure water-resistance*" %}


### Temperature, Humidity and Illuminance

The microclimate sensor tower is assembled from [custom 3D-printed parts](https://github.com/Nature40/Sensorboxes-Design/tree/master/printdesigns/version%20_0/radiation%20shield), which contain a Temperature and Humidity as well as a Lux sensor. 


{% include figure image_path="/assets/images/moon/lmst_CS.png" alt="LMST" caption="*The top of the lux sensor is covered with a a class plate cut from a microscope slide*" %}




### Microphone

The microphone is used to record the singing of birds. This data can be used by a machine learning algorithm to identify bird species. Bird species are an important indicator for biodiversity in forest ecosystems.
Due to the ranges of quality and price on the microphone market, two alternating microphones have been chosen to attach to the Planet, both models are tested alternately.  

The RØDE – Smartlav Microphone is composed of following components. 

- RØDE – Smartlav
- external soundcard UGREEN USB
- Design - Audio y adapter cinch cable 3.5mm socket to cinch cable
- acoustic cloth 2.0 - 4102/B2 hydrophobic
- metal wire 0.9 mm

{% include figure image_path="/assets/images/planet/rode.jpg" alt="The RØDE – Smartlav Microphone" caption="*The RØDE – Smartlav Microphone*" %}


The second preference is a lower price Microphone. 

- Foxnovo SF-555
- acoustic cloth 2.0 - 4102/B2 hydrophobic
- metal wire 0.9 mm

{% include figure image_path="/assets/images/planet/foxnovo.jpg" alt="The foxnovo microphone" caption="*The foxnovo microphone*" %}

Both microphone types have there individual 3D printed microphone tower, published [here]({{site.baseurl}}/pages/parts/printing/). 

To address the problem of incoming water, the microphone will be sourounded by an hydrophobic acoustic cloth. First an acoustic cloths carrier is constructed on top of the microphone tower using the metal wire. 


{% include gallery id="panel1"  caption= "*Construction steps 1-3*" layout ="third"  %}


{% include gallery id="panel2"  caption= "*Construction steps 4-5*" layout ="third"  %}

Now the acoustic cloth can be attached.


{% include gallery id="panel3"  caption= "*Attaching the Microphone Protection steps 1-3*" layout ="third"  %}

Finally the microphone incl. the tower can be glued on the box. 

{% include figure image_path="/assets/images/planet/mic.jpg" alt="Placing the microphone incl. tower on the box" caption="*Placing the microphone incl. tower on the box*" %}

### 6. Camera

A camera is used to monitor the canopy from below crown surface. The collected data can be used to calculate the greenness-index to compare it with UAV generated aerial RGB-images. Further it can be used to monitor vegetational growth and animal wildlife detection.

As a camera the [Raspberry Pi Camera Module v2.1]((https://www.raspberrypi.org/products/camera-module-v2/)) with a [custom 3D-printed mount](https://github.com/Nature40/Sensorboxes-Design/blob/master/printdesigns/version%20_0/camera_case/Camera_case.stl) is used. 

### 7. Base Plate  

The Raspberry Pi, the Real-time clock as well as DC/DC Converter are directly attached to the [3D printed]({{site.baseurl}}/pages/parts/printing/) baseplate, using 4x C 2,9 X 13 H countersunk-head tapping screw for the Raspberry Pi, hot glue for the real-time clock. Using Jumper Cables the Real-time clock is connected to the Raspberry Pi's **G**eneral **P**urpose **I**nput **O**utput (GPIO) interface. 

{% include figure image_path="/assets/images/planet/baseplate.png" alt="3D printed mounting plate" caption="*3D printed mounting plate*" %}


Take one +/- rail from a Breadboard and glue it on the bottom side of the Raspberry Pi mounting plate and connect it with the jumper-cables: red for (+) and black for (-).

Connect the USB-power-cable to the Raspberry Pi. Put the Powerbank on the inner side of the containment box cover.

{% include figure image_path="/assets/images/moon/pi_mount_rdy.png" alt="Raspberry Pi mounting" caption="*Raspberry Pi mounting*" %}

### 8. System and Storage 

The Samsung MB-MC32GA MicroSD card is directly plugged into the Raspberry Pi, the MicroSD card contains the purpose-build operation system. A [freely available repository](https://github.com/Nature40/Sensorboxes-Images) collects software and hardware descriptions and contains distribution definitions as well as configuration files for sensorboxes.

### 9. Hall Sensors

Connect the jumper-cables and adjust the sensitivity by turning the adjusting-screw on top of the sensors. Use a magnet to test the reaction: The Hall-sensor's lamp should glow if it senses a magnetic field.

{% include figure image_path="/assets/images/moon/pi_mount_rdy.png" alt="Exact hall sensor positioning is crucial" caption="*Exact hall sensor positioning is crucial*" %}


### 10. Wiring Diagram

Connect the wires according to this Frizzing diagram:

{% include figure image_path="/assets/images/moon/frizzing.png" alt="Frizzing diagram of the sensor box wiring" caption="*Frizzing diagram of the sensor box wiring*" %}


Seal all space between the Sensors and the containment box with silicon or glue. Further seal all openings from the inner side of the containment box leading to the sensors with silicon or glue.


{% include figure image_path="/assets/images/moon/final.png" alt="Seal all space between the Sensors and the containment box with silicon or glue" caption="*Seal all space between the Sensors and the containment box with silicon or glue*" %}




## Parts List

These parts are required to build a sensorbox type planet.

### Basis
- [Spelsberg TK PS 2518-11-o](https://www.spelsberg.com/industrial-housing/with-/-without-metric-knock-outs/11090801/) (180 x 254 x 111 mm)
	- External hinge set [Spelsberg ASS-gro](https://www.spelsberg.com/small-distribution-boards/ak-air-distributor-14-70te/19000501/)
- [Raspberry Pi 3 B v1.2](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
	- Heat Sink Set
- [DS3231 real-time clock](https://datasheets.maximintegrated.com/en/ds/DS3231.pdf)

### Power Supply
- EasyAcc PB26000MS Powerbank, 26000 mAh
	- Charge-through
- microSD QI Charging Pad

### Sensors

#### Microclimate
- [Adafruit TSL2561 Digital Luminosity/Lux/Light Sensor Breakout](https://www.adafruit.com/product/439)
- AOSONG AM2302 Temperature Sensor

#### RPi Camera
- [Raspberry Pi Camera v2.1](https://www.raspberrypi.org/documentation/hardware/camera/)
- [Custom 3D-printed mount](https://github.com/Nature40/Sensorboxes-Design/blob/master/printdesigns/version%20_0/camera_case/Camera_case.stl)

#### Microphone

- [Acoustic cloth 2.0](Acoustic cloth 2.0) - 4102/B2 hydrophobic
- Metal wire 0.9 mm

##### Option 1: RØDE – Smartlav Microphone
- RØDE – Smartlav
- external soundcard UGREEN USB
- Audio y-adapter cinch cable 3.5mm socket to cinch cable

##### Option 2: low-price microphone 
- Foxnovo SF-555

### Storage
- Samsung MB-MC64GA MicroSD 64GB

### Lift Car
- 6x Rolls
- 2x [Joy-IT KY-024](https://joy-it.net/en/products/SEN-KY024LM) Hall Sensor

### Mounting
- [Custom 3D-printed sensor mount](https://github.com/Nature40/Sensorboxes-Design/blob/master/printdesigns/version%20_0/lift_box_topper/lift_box_topper_finder.stl)
- [Custom 3D-printed base plate](https://github.com/Nature40/Sensorboxes-Design/blob/master/printdesigns/version_1/gondola/raspi_hex_mount_plate_V1.stl)
	- Pi: 4x C 2,9 X 13 H countersunk-head tapping screw (DIN 7982)
	- Box: 5x M 4,0 x 12,0 countersunk-head screws DIN 965
- USB Sound Card, Powerbank, QI Charger: 3M Dual Lock Thin SJ 457 D
- Hall sensor, power rail: Hot glue
- Silicone (for sealing cable holes)
- 6x Screws M4 x 20 (rolls)

### Wiring 
- Breadboard Power Rail
- Hall Sensor: 6x Jumper Wire female-female
- RPi: 2x Jumper Wire female-male
- RTC: 4x Jumper Wire female-female
- Microclimate Tower: 8x Jumper Wire female-male
- Camera: 30cm CSI camera cable
