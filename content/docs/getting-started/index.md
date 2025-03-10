---
title: Getting Started
weight: 10
---

{{< blocks/section type="row" color="white" >}}
{{% blocks/feature icon="fa-1" %}}
Get your hands on a device

[Read More](#choose-your-device)
{{% /blocks/feature %}}
{{% blocks/feature icon="fa-2" %}}
Flash your device

[Read More](#flash-the-firmware)
{{% /blocks/feature %}}
{{% blocks/feature icon="fa-3" %}}
Configure your device

[Read More](#configure-your-device)
{{% /blocks/feature %}}
{{< /blocks/section >}}

## Choose Your Device

- Heltec Boards: Budget-friendly and beginner-friendly.
- LilyGo & Wisblock Rak Boards: Advanced boards offering maximum flexibility for customization.

If you have access to a 3D printer, explore these amazing cases:

- Heltec V3 Mini Case
- RAK19007/RAK5005 Case
- T-Beam V1.x Case
- T-Beam Supreme Case

## Flash the Firmware

After selecting your device, use the [Meshtastic web flasher](https://flasher.meshtastic.org/) to install the software.
It's quick, straightforward, and backed by excellent documentation.

## Configure Your Device

1. Connect to your device

2. Set your Lora Region to United States

In most cases where we are located in Iowa we'll need to use the 915 mhz bands of LoRa

If you plan on participating in the meshmap you'll need to turn on Ok to MQTT.
More information [here](https://meshtastic.org/docs/configuration/radio/lora/#ignore-mqtt).

![LoRa Config Screen](lora-wan-config.jpg)

5. Set your hop count.

Current in Iowa it's a bit sparse for coverage.
It might be worth turning up for the recommended 3 hops

Information on [Meshtastic's docs](https://meshtastic.org/docs/configuration/radio/lora/#max-hops).

6. Add Channels for Private configuration

Use These QR Codes to Add the additional IROMesh Channel to your node.
The Public Channel is available to everyone, but the IROMesh Channel will give us a little better place to communicate among the group.

![IRO Mesh channel config](iro-add.jpg)

7. Name Your Device

Be Found Easily by naming your device! If you are already a licensed Amateur Radio Operator you can opt to put in your call sign

![Device name config](device-name.jpg)

## Have Fun

## Join the Community

Have questions or want to connect? Find us on [Discord](https://discord.gg/jHBywwPJD8) and join the conversation with Iowa Radio Operators!
