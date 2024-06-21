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
- Display
- portable power source: Power Bank

##### Useful Hardware
- Real time clock(hardware clock)
- Case

#### Hardware in deep explanation (alternatives)

##### The Base of our little Friend
I've used a Raspberry Pi Zero W (Pi0W) but other Pi's are as well supported by the image we're gonna use.  
By time of this guide the following Pi's are supported:
- Raspberry Pi Zero W
- Raspberry Pi Zero 2 W
- Raspberry Pi 3
- Raspberry Pi 4
- Raspberry Pi 5

I recommend the Pi0W or Pi02W, because the have the charm of the Pwnagotchi. They are cheap and small that's what makes the Pwnagotchi so special. 
