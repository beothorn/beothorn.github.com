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

![Starting node red](/assets/img/startNodeRed.png)

You are ready to continue.

## Setup Alexa

You will need to create a fake device so you can listen to alexa turn on commands.

To be able to receive commands from your alexa to turn on a device follow [this tutorial](/2020/11/05/Redirect_rasp_pi_port.html)

## Setup arduino

<script src="https://gist.github.com/beothorn/d62ada134b78c137c32953071d01a6ed.js"></script>

https://gist.githubusercontent.com/beothorn/d62ada134b78c137c32953071d01a6ed/raw/59e764c92dd520ec81ec9e3306fc170b0203eef0/TempAndHumidityKY015.c

## Schedule continuous temperature reading

<script src="https://gist.github.com/beothorn/f2fdbe3a3121ffff66275fedc4bd0d0b.js"></script>

https://gist.githubusercontent.com/beothorn/f2fdbe3a3121ffff66275fedc4bd0d0b/raw/d972f1d08bd809027e242f9b6095807955be87ba/readTemp.py

## Login on amazon 

## Links

[How to setup alexa to say something](https://peyanski.com/alexa-tts-how-to/)