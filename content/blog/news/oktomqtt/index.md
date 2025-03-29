---
date: 2025-03-28
title: Ok to MQTT (Why We Need It)
author: Calvin Jutting ([@KN0CTJ](calvin@iowamesh.net))
---

## MQTT (The almost forbidden subject)

What do you think of when I say MQTT? In the nerd spaces I normally occupy that would be Message Queuing Telemetry Transport. In most cases, it’s a great way of getting telemetry data out of IOT devices into some sort of central repository. 

In the early days of Meshtastic, it would seem that MQTT was a great way of getting data across larger places especially if there wasn’t enough RF to carry these messages along the way. With growing privacy concerns the developers at Meshtatsic opted (and introduced in 2.5 firmware) to include properties in the packet that ignore MQTT or even permit MQTT.

A user on Reddit I think said it the best:
*“MQTT is one of the best, and apparently worst parts of the project. I do feel that currently, privacy and security is at risk when using public MQTT (even the meshtastic server), to the point where people could get hurt. I don't think people should avoid the project, but I do think people should know the extent of the issue, an issue so severe the team has been trying to sweep it under the rug (damage control). They even mute users who bring up the issue in the discord.”* - [Reddit Source](https://www.reddit.com/r/meshtastic/comments/1f6xdqf/current_state_of_mqtt/)


 From the Offical Documents that explain the settings:

`Ignore MQTT
Setting this to option to 'true' means the device will ignore any messages it receives via LoRa that came via MQTT somewhere along the path towards the device. Note this only works when your device and the MQTT node are running at least firmware version 2.2.19.`

`OK to MQTT​
Acceptable values: true, false
Default is false. When set to true, this configuration indicates that the user approves their packets to be uplinked to MQTT brokers. If set to false, nodes receiving your packets are requested not to forward packets to MQTT. This configuration only applies to Channels configured with the defaultpsk and eventpsk keys set in the Meshtastic Firmware; Channels with custom keys ignore this setting.
Important: This is not a cryptographic solution but a polite request that is enforced in the official firmware`

So if you’ve stuck with me this far, Thank You. There is an end in sight, I promise,

IowaMesh relies on MQTT right now to keep big parts of the state connected. Without it, there’d be isolated patches where people couldn’t communicate with each other. Our ultimate goal is to shift entirely to RF, but that’s still a work in progress. Once the network is more built out, we’re planning to cut MQTT use down. So for all of you RF purests out there I urge you to consider the bigger picture here.

We take your privacy seriously. If a packet comes into the mesh marked "Ignore MQTT," we honor that—always have, always will. The Meshmap site has supported this from day one. But there are some things you should know about how this works.

If you choose to ignore MQTT or don’t enable the "OkToMQTT" setting, your messages won’t show up in the Text Messages list on Meshmap. Most head-end nodes have "OkToMQTT" turned on, so your messages will still make their way through the mesh, but they won’t be collected or displayed.

The other thing to keep in mind is that without MQTT, some messages might only reach certain people—or maybe not get through at all, depending on how the mesh is set up that day. RF will still work as expected though, so there’s always that!

