iOS-meets-Arduino
=================

Documentation of my talk [iOS meets Arduino](http://www.developer-week.de/Programm/Veranstaltung/(event)/14147) at the [Developer Week 2014](http://www.developer-week.de) in Nuremberg, Germany. You can find the slides to this talk on [slideshare](http://www.slideshare.net/jensmeder/ios-meets-arduino).

This repository references all libraries and examples that have been shown during the talk. If you want to check them out all at once simply clone this repository and then run the following commands:

```
cd iOS-meets-Arduino
git submodule update --init
```

## Overview

1. [Apple's MFI program](README.md#apples-mfi-program)
2. [Head phone jack](README.md#head-phone-jack)
3. [Bluetooth Low Energy](README.md#bluetooth-low-energy)
4. [Lightning / Dock serial cable](README.md#lightning--dock-serial-cable)
5. [WiFi](README.md#wifi)

## Apple's MFI program

Apple wants to guarantee a great user experience with all its products. The MFI program (Made for iPhone / iPad / iPod Touch) is to hardware accessories what the app store is to apps: a quality gate (well, it should be but that's a different story). 

Becoming member of the MFI program is not that easy. You have to fulfill certain prerequisites that you can find in their [FAQ](https://mfi.apple.com/MFiWeb/getFAQ). To sum it up: You have to be a company with money. Fortunately, there are ways to circumvent the MFI program.

## Head phone jack

You might remember the times when a high speed internet connection had 56kbit/sec. At that time we have used signal modulation to transmit digital data via analog land lines. One such modulation technique is FSK (frequency shift keying). With the help of FSK we can transmit data between iOS devices and Arduino via the head phone jack.

FSK uses two different frequencies to represent high and low states (e.g., 4 kHz for low and 8kHz for high) by modulating a base carrier, e.g., a sine curve. Given a baud rate we can determine the duration of a single bit, e.g., a baud rate of 1000 bit / sec equals a bit duration of 1ms. If the majority of frequencies in this interval equals the frequency for a high state then we have a high state, etc. . 

## Bluetooth Low Energy

## Lightning / Dock serial cable

## WiFi

WiFi is an easy option to connect your Arduino to an iOS devices. There are several Arduino WiFi shields available. One thing they have in common: they are all kind of pricy (ca. 65€). An alternative to buying a shield: buying an Arduino Yun (ca. 60€). 

The Arduino Yun combines an Arduino Leonardo with an Atheros AR9331 that communicate with via a serial interface. The Atheros processor runs a special version of OpenWRT called OpenWRT-Yun. The Yun provides Ethernet and WiFi support, a USB host port, and a micro-SD card slot. Compared to WiFi shields you get several advantages:

1. You can do resource intensive computation on the Atheros / OpenWRT side and then just pass the result over to the Arduino side.
2. You save space for your Arduino sketch since you do not have to include the WiFi library.
3. You can communicate with the Arduino either via SSH or a REST API.
