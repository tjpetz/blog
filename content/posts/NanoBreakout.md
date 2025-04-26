+++
date = '2020-05-09T17:50:01-04:00'
draft = false
title = 'SWD Breakout and Breadboard for Nano 33 BLE Sense'
+++

The Arduino Nano 33 BLE (Sense) and the Nano 33 IoT expose SWD pads on the bottom of the board.  These pads expose the SWD interface that enable debugging when used with an SWD compatible debugger such as the Segger J-Link Mini EDU (https://www.segger.com/products/debug-probes/j-link/models/j-link-edu-mini/).

The pads on the bottom of the Nanos are very small (and as we’ll see later quite fragile).  Normally you would use some form of test fixture and pogo pins to connect to the pads.  I don’t have that.  Some approaches show soldering dupont wires to the pads and then connecting to the J-Link via and adapter.

I’ve used a solderless breadboard with my Nano 33 BLE Sense and an Adafruit SWD Breakout Board (https://www.adafruit.com/product/2743) to build a debugging and breadboard setup.

![Breadboard layout](/assets/images/NanoBreadboard/pic1.jpeg)
