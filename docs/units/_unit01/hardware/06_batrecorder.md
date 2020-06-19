---
title: BatRecorder
toc: true
toc_label: Content
header:
  image: /assets/images/01-splash.jpg
  image_description: "Image Panel Natur 4.0 Sensorboxes"
  caption: "Images Natur4.0 / CC0"
---

# System design
The BatRecorder is a self-invented hard and software for saving audio and video data of flying bats.
Therefor we integrate the vhf technologie into a system with ultrasonic microphones, infrared cameras and infrared led spots. 
So we can detect bats by microphone or vhf signals and then start the audio and video captcha process.

## Three different sensorboxes in one design
With our design we can build boxes with three different configurations:
- BR_audio boxes: record audio files when vhf subsystem triggers
- BR_video boxes: record video files when vhf subsystem triggers
- BR_combined boxes: record video and audio files when the vhf subsystem or audio system triggers

more configurations are possible for example a audio box without vhf system and only triggered by bat calls

{% include figure image_path="/assets/images/bat_recorder/BR_combi.jpeg" alt="A BR_combi box build up for a test case*" %}

## Live view 
For the deployment and live monitoring nearby the camera a wifi is present and enddevices can log in.
After logging in a request in a webbrowser can be made and the live camera view is shown.

{% include figure image_path="/assets/images/bat_recorder/live_view.jpeg" alt="Hingeset" caption="*Here we see the live view for a BR_video box*" %}

additional all camera setting and some schedules can be set.
So it could also be a nice peace of software and maybe also the hardware also for camera traps because a bit of motion detection is also present. 

## Components of the BatRecorder 

For the BatRecorder we used:
- Raspberry pi 
- Realtime clock
- RTL-SDR-Stick 
- Ultra sonic usb microfone 
- vhf antenna 
- NoIR Rasperry pi camera 
- IR LED spot

{% include figure image_path="/assets/images/bat_recorder/BR_inner.jpeg" alt="Hingeset" caption="*The inner parts of the BR boxes*" %}