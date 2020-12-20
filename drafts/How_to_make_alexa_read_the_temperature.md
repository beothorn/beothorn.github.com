---
title: How to make Alexa read the temperature
layout: singlePost
comments: true
---

In this post I will show you how can you make alexa read the temperature and humidity using a raspberry pi, one arduino and a temperature sensor.

I guess it is probably cheaper to just buy some hardware that does that, but not that cool :)

The idea is having a node-red server running on the raspberry pi and listening to calls from Alexa. The end result will be calling "Alexa, turn on temperature" will trigger a custom message on Alexa saying the humidity and temperature.

## What you will need

- One Alexa device, in my case I used an echo dot 3rd generation
- A computer to host node-red, in this tutorial I used a raspberry pi 4
- One arduino
- A KY-015 Temperature and humidity sensor module
- Basic coding skills

## First step, node-red

Node-red is a flow-based development tool for visual programming. It looks like this:

IMG GOES HERE

The great thing about node-red is the easiness of connecting functions and the availability of plugins that do almost everything.

With node-red we will be able to run a script that reads the tempreature from the sensor on arduino and saves it into a file and the feed this file 
for Alexa to read.

To install node-red follow the instructions at [https://nodered.org/docs/getting-started/raspberrypi](https://nodered.org/docs/getting-started/raspberrypi). Mainly you just execute the installer script. Pay attention that it will override your nodejs with a different version.

On the command line run:

```
bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)
```

Then register it as a service:

```
sudo systemctl enable nodered.service
```

Restart the pi.

Find out your IP address
```
ifconfig
```

Under wlan you will find it, in my case it was 192.168.0.31 .

Then from a browser on the same network access http://192.168.0.31:1880/ (use the ip from ifconfig).

If you see this:

IMG

You are ready to continue.