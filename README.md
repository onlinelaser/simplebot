# SimpleBot.

## Overview

This is one of the most simple robots you can make. Features are:

* quick to put together (about an hour)
* very hackable (it can be built with cardboard or laser cut so very easily modifiable)
* can move pretty fast (at full tilt it will go about half a metre a second - faster with more juice for the servos!)
* very extendable (much of the magic happens in code and sensors can be easily fed in)
* Cheap (costs about $100 which is very cheap for your first robot)

This bot is an adaptation of the excellent [SumoBot Jr](https://github.com/makenai/sumobot-jr/) made by [Paweł Szymczykowski](http://twitter.com/makenai) but doesn't require laser cutting wood or plastic though you can if you want something a bit more long lasting.

## Capabilities

This is a tethered robot, meaning it stays connected to your computer via a USB cable. This means you can get your computer to do all the hard work to provide interface control (say a web page or an app) and processing (computer vision if you attached a webcam for example!).

This is the very first prototype, put together in about 30 minutes one evening.

![SimpleBot](docs/img/simplebot-proto.jpg)

Further iterations led to more refined designs such as this which has wifi capability.

![SimpleBot MkII](docs/img/simplebot-wifi.jpg)

Once done you can reuse all of the components to make a bigger, badder, faster robot and switch the cardboard for more durable elements such as laser cut wood or plastic if you desire. We've even supplied the SVG and DXF files to do exactly that.

Add a raspberry pi and you get a SimplePiBot which can be made fully autonomous.

![SimplePiBot](docs/img/simplepibots.jpg)

## Materials needed

The following are the various components you need to get hold of to make your SimpleBot:

* An Arduino - just about any type will do. We use Arduino Nanos because they are small and relatively inexpensive, but an Uno, Eleven, LeoStick or other Arduino will work just as well.
* 4xAA Battery holder - Provides the power for your motots. You'll want some batteries too - rechargables are best if you can afford them.
* Mini Breadboard - This allows you to wire things together without soldering. There's plenty of colours to choose from.
* 2x Continuous Rotation Servos - These drive the wheels. *Don't for get you need two or you'll be making a unicycle-bot*
* Jumper wire - Wire to connect everything together. A mix of MM, MF and FF is good to you can connect jumpers to different types of pins.
* Ultrasonic Range Finder (also called a ping sensor) - This allows your bot to detect how far things are away using sonar.


### Suppliers

There are a range of suppliers you can get things from. Here are a selection:

[JayCar](http://www.jaycar.com.au) provide a range of basic components but not the full range. Mostly good for basics like wire and tools.

[Freetronics](http://www.freetronics.com) are a local Melbourne hardware design business. They produce some of the highest quality electronics in the world and they do it all Open Source. They even build satellites! If you're [just after an arduino](http://www.freetronics.com/collections/arduino/products/eleven#.UjuVQxIW3S0) and not the whole bot then support an Aussie business doing high tech work.

[LittleBird Electronics](http://littlebirdelectronics.com) has been a big part of the maker community over the last few years, they carry a big range of components and they have excellent customer service. (Total price from LBE is about $90)
 
[TronixLabs](http://tronixlabs.com/) are a Melbourne-based supplier who stock enthusiast and hobbyist electronics, robotics, single-board computers etc, and you can find equivalent parts listed [here](http://tronixlabs.com/nodebots/). (Total price from TronixLabs: $65)

We'll have cardboard, cable ties and other prototyping stuff available on NBD to help build your very own bot but other things you might want to bring could include:

* Laser pointer to make an annoying cat toy.
* Stickers to bling out your bot.
* Spikes to take out others; Ben Hur or Mad Max style.
* USB WebCam if you want to give your bot some vision.
* USB cable extender if you want some range.

# SETUP

To setup your SimpleBot we're assuming you have Arduino and NodeJS installed already. 

## Flashing the arduino

Load up the firmware/arduino/SimpleBotFirmata sketch.

Compile and upload it to your arduino.

Wire up your SimpleBot and then you have an examples folder with ping.js and simplebot.js which you can use as a base for everything else.

The wiring diagrams are provided here:

Schematic:

![SimpleBot schematic](examples/wiring/basic_wiring_schematic.png)

Breadboard:

![SimpleBot Breadboard diagram](examples/wiring/basic_wiring_bb.png)

# Examples

## Driving over Bluetooth

You can use bluetooth to drive the simplebot but it's not for the faint of heart. Get a bluetooth module and configure it per [this wiki entry in J5](https://github.com/rwaldron/johnny-five/wiki/JY-MCU-Bluetooth-Serial-Port-Module-Notes). This is a mandatory.

Once you've got your bluetooth set up, you should see it in your serial ports.

Simply go:

    node examples/simplebot.js /dev/tty.SERIALPORT

Changing the device path to whatever yours is. You should now be able to drive using wireless over bluetooth. 

## Game controller

If you happen to have a playstation controller then you can use the sb-controller.js example to drive your simplebot using a console controller which is pretty cool.

## Driving using wifi

You can use a simple serial wifi module to make your SimpleBot work over wireless (increased range, no BT headaches). Check out [this gist for more details](https://gist.github.com/ajfisher/1fdbcbbf96b7f2ba73cd).

# LICENSE

This SimpleBot repo is licensed using the MIT license for all components.

Firmata implementations are modifications of [https://github.com/firmata/arduino/](Firmata for Arduino) by [https://github.com/soundanalogous](Jeff Hoefs @soundanalagous) and others and is used according to the GPL.

Firmata modifications include merged components of the [https://github.com/jgautier/arduino-1/tree/pulseIn](pulseIn code) as created by [https://github.com/jgautier](Julian Gautier @jgautier).


