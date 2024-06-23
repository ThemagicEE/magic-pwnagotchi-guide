---
tags: hacking, pwnagotchi, guide
aliases: Hacking Pet
created: 21-06-2024 21:34:40
modified: file.mday
---


## Introduction


### What is a Pwnagotchi
Pwnagotchi is an open-source project that combines a Raspberry Pi, an e-Paper display, and various scripts to create an autonomous Wi-Fi hacking device. It leverages artificial intelligence to learn from its environment, capture Wi-Fi handshakes, and grow more effective over time. As it "learns," your Pwnagotchi develops its own personality, interacting with you through its e-Paper display, making the experience both educational and entertaining.

![[Pasted image 20240623163443.png]]

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

I use: https://www.amazon.com/SanDisk-128GB-microSDXC-Memory-Adapter/dp/B0B7NTY2S6/ref=sr_1_3?sr=8-3

##### Micro-USB cable
You just need a micro-USB cable that can transfer data (not just charging). Most of you should have one of these laying around, including myself. The cable should preferably support fast data transmission (at least the speed of your SD card).

Like this one: https://www.amazon.com/Amazon-Basics-Charging-Transfer-Gold-Plated/dp/B0711PVX6Z/ref=sr_1_1_ffob_sspa?sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1
##### Pins to install the display
You will need to solder pins on your Pi to install the display, or you can buy a Pi with pre-soldered pins, like I did. The Raspberry Pi 3-5 models have all pins installed, but the RPi0W and RPi02W do not have any pre-installed pins in their default versions. However, there is a version with an "H" (RPi0WH) where the "H" means that pins are already installed.


![[Pasted image 20240623160712.png]]  

![[Pasted image 20240623161037.png]]

##### Display(E-Paper Hat)
There are many displays/E-Paper HATs that work. To check if your e-paper HAT is supported, just go to the following website and press "Ctrl + F" on your keyboard to search for your display (e.g., waveshare_4). Write everything together with no spaces, or use underscores.