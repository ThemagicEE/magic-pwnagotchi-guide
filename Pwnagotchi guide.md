---
tags: hacking, pwnagotchi, guide
aliases: Hacking Pet
created: 21-06-2024 21:34:40
modified: file.mday
---


## Introduction


### What is a Pwnagotchi
Pwnagotchi is an open-source project that combines a Raspberry Pi, an e-Paper display, and various scripts to create an autonomous Wi-Fi hacking device. It leverages artificial intelligence to learn from its environment, capture Wi-Fi handshakes, and grow more effective over time. As it "learns," your Pwnagotchi develops its own personality, interacting with you through its e-Paper display, making the experience both educational and entertaining.

## How to build one

### Hardware you need

#### Short From (Recommended Hardware)

##### Needed Hardware
- A Raspberry Pi Zero W (Heart/Base) 
- micro-SD card(min. 16GB, better more and min. 100 MB/s, better more)
- Micro-USB cable which can transfer data(very important)
- Pins (Pi with pre installed pins or solder them our self)
- Display
- portable power source: Power Bank

##### Useful Hardware
- Real time clock(hardware clock)
- Case

#### Hardware in deep explanation (alternatives)

##### The Base of our little Friend
I've used a Raspberry Pi Zero W (Pi0W), but other Pis are also supported by the image we're going to use. As of this guide, the following Pis are supported:

- Raspberry Pi Zero W (H)
- Raspberry Pi Zero 2 W (H)
- Raspberry Pi 3
- Raspberry Pi 4
- Raspberry Pi 5

I recommend the RPi0W (Raspberry Pi Zero W) because the original project was built for this Pi. That's also the Pi I will be using in this guide. The other models should work fine too, and the installation process is similar.

##### SD card
Any micro-SD card should work as long as it has more than 16GB of space and can write at over 100 MB/s. 

I would recommend an SD card with around 128 GB capacity because this way you don't have to worry about space and you can capture handshakes for a long time.
A faster SD card makes sense too, because it allows for faster boot times and faster data transmission.
