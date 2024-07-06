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
- A Raspberry Pi Zero W(H) (Heart/Base) 
- micro-SD card(min. 16GB, better more and min. 100 MB/s, better more)
- Micro-USB cable which can transfer data(very important)
- Pins (Pi with pre installed pins or solder them our self)
- Display (Waveshare V4)
- portable power source: Power Bank

##### Useful Hardware(but not needed)
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
There are many displays/E-Paper HATs that work. To check if your e-paper HAT is supported, just go to [this website](https://github.com/jayofelony/pwnagotchi/blob/33ff5a0bf85ad277005ca6feaac7f16968ac5a31/pwnagotchi/ui/display.py#L67) and press "Ctrl + F" on your keyboard to search for your display (e.g., waveshare_4). Write everything together with no spaces, or use underscores(sometimes you need to try both methods to find your display). 
I've used the [2.13inch E-Ink display by Waveshare](https://www.waveshare.com/2.13inch-e-paper-hat.htm) and had no problems with it but any other display in that list should work too. 

You could even choose not to use a display, but I believe that the display makes this project special and distinguishes it from other WiFi hacking tools.


##### Power source
While you are setting your little friend up, your PC will be the power source. However, if you want to use it on the go, you will need a power bank. Any power bank that you can connect your micro-USB cable to should work. 
From my experience, a power bank with around 5000 mAh can run the Pwnagotchi for about 10-12 hours.


##### Real time clock
A real time clock can come in handy to get accurate time stems on your captured handshakes.
But it's not nesseray by any means. I will show in this guide how to install one but if you don't one, you can just skipp that part of the guide. I just believe that it's very helpful to match you handshakes with the location you've been.  

Any I2C model can be used(PCF8523, DSL1307 or DS3231 based)


##### Case
A case is very use full to protect your Pwnagotchi. There are a few different options when it comes to cases. You could 3d Print one, use a pre build case or use a paper box, like I did. I just used the box of the display and padded it a little bit(like shown on the picture).

![[IMG_20240624_175049.jpg]]

If you wanna 3d Print a Case, there are many print file from the community you can use just choose one.  
Here are a few: https://www.thingiverse.com/thing:3920904




### Building/Setup Tutorial

#### Assemble Pi and Display
**Get your Pi and Display ready!**
![[Pi and Display.jpg]]

Now we have to connect them both. You see these "holes" on the display? These match perfectly with the pins on our Pi. Just stick them together.

Like this:
![[Pi and Display assambled.jpg]]

You need to push the display all the way down, even though it might feel wrong. It has to be fully connected; otherwise, you won't get a picture.

Like shown on following images:
![[IMG_20240625_153509.jpg]]

![[IMG_20240625_153612.jpg]]

Hardware-wise, you are finished. I suggest installing a case and a real-time clock after configuring everything. This way, you can easily disassemble your friend if something doesn't work.


#### Flashing the Image

##### What you need
Get the the latest image for your Pi here: 
https://github.com/jayofelony/pwnagotchi/releases

If you use a **Raspberry Pi Zero W(H)**, use the **32 bit** version.
For **any other** mentioned above, use the **64 bit** version.

To flash the image to the SD card, you need the [**Raspberry Pi Imager**](https://www.raspberrypi.com/software/).

_Click_ "Choose OS," scroll all the way down, and select "Use Custom." Navigate to your Downloads folder and choose the downloaded image. In the final step, select your SD card and _click_ "Write".

This may take a while, depending on your SD-card and reader.


#### First Boot
##### Starting Pi up
Insert your SD card into your Pi and grab your micro-USB cable. Your Pi has two USB ports, as shown in the image:

![[IMG_20240627_203440.jpg]]

Connect your Pi through the Data Port with your PC. 

**Now wait!!!** Don't touch your friend, don't disconnect him, just wait. 

The first boot can take up to 25 minutes Go touch some grass and come back after a while.

##### Establish Connection to Pi
###### Finding the device
Open the "Device Manager" by searching for it in your taskbar. And open it.
![[Pasted image 20240627215031.png]]

After a while, either a "USB Ethernet/RNDIS" Gadget or a device under "Ports" should appear. If an RNDIS Gadget appears, you are good to go; otherwise, we will have to configure it to appear as one.
![[Pasted image 20240627215326.png]]

To make it into an RNDIS device, you will need to download the RNDIS drivers [here](https://modclouddownloadprod.blob.core.windows.net/shared/mod-rndis-driver-windows.zip).

Right-click the device and select "Properties."
![[Pasted image 20240627220154.png]]

Then click on "Driver" and select "Update Driver."

Click "Browse my computer for drivers."
![[Pasted image 20240627220341.png]]

Navigate to your **unzipped** drivers folder, and then click "OK."
Your Pi should now be shown as "RNDIS Gadget".

Now you're good to go, and we can almost SSH into our Pi.


###### Configure Network Settings  

To SSH into our Pi, we first need to configure the network settings of the Pi.

Open the settings on your PC and navigate to the **"Network & internet"** tab.

Next, click on **"Advanced network settings"**.

You should see your RNDIS Gadget there:
![[Pasted image 20240703210423.png]]

Expand the menu of your ***main network*** and click on "**Edit**".
![[Pasted image 20240706200243.png]]
In the new menu click on "**Sharing**" and double click it.

Enable internet sharing and choose your pwnagotchi(in my case "Ethernet 2").
![[Pasted image 20240706200819.png]]

Accept everything and go back to the "**Advanced network settings**".

Expand the menu of your Pi and click on "**Edit**".
![[Pasted image 20240703211052.png]]

In the new menu search for "**Internet Protocol Version 4(TCP/IPv4)**" and double click it:
![[Pasted image 20240703211541.png]]


Now enter following data in the brackets:
***Ip address***: "10.0.0.1"
***Subnet mask***: "255.255.255.0"

***Preferred DNS server***: "1.1.1.1"
***Alternate DNS server***: "8.8.8.8"

![[Pasted image 20240703215811.png]]

Accept everything, and now we can SSH into our Pi.

***Important***
If you reconnect your Pi to your PC, you will have to disable network sharing and enable it again and you have to repeat the above shown steps.
###### SSH into the Pi and change the password
Open up "CMD" by searching for "Command Prompt" in the taskbar:
![[Pasted image 20240703214104.png]]
Open it up.
Type "**ssh pi@10.0.0.2**" and click enter.

The password is "**raspberry**".

Now we have to change the password of our pi.
Type "**passwd**" and click enter to change the password for SSH excise. 


###### Basic configuration 
Run this command "**sudo pwnagotchi --wizard**" to setup a basic config-file.

You will setup following things with this command:
 - the name for your pwnagotchi
 - whitelist of networks(networks to ignore(like your home network))
	 - you can find the information needed for this in the properties of your home network.
- Enable or disable BT-tethering(disable it for now I will cover this later on)
- Enable the display and choose the color of it