---
date: 2025-03-28
title: Meshtastic v2.6 A Feature-Packed Release
author: Chad Porter ([EMB3D](emb3dthreat@proton.me))
---

## Meshtastic v2.6: A Feature-Packed Release
Meshtastic recently announced the public release of Meshtastic v2.6, a major update that has been years in the making. This release introduces several exciting new features and improvements, making it the most feature-packed Meshtastic to date. Here's a summary of what's changed in Meshtastic v2.6.

## Key Features in 2.6
### 1. Next-Hop Routing
After extensive preparation, implementation, simulations, and real-life testing, Meshtastic introduced a more efficient routing protocol for direct messages called "next-hop routing". This new protocol is designed to optimize the delivery of direct messages.

Meshtastic uses a "managed flood" approach for message delivery, where multiple devices attempt to relay messages. While effective, this method can lead to network congestion especially for direct messages. Next-hop routing addresses this by designating a specific device to relay the packet, reducing unnecessary transmissions and improving overall network efficiency for direct messages. If a node moves or RF conditions change, the next-hop designation may become invalid. In such cases, the node will fall back to managed flooding at the last retransmission attempt if it does not hear its next-hop relay.

**Next-Hop Header:** The last two unused bytes of the unencrypted Meshtastic header denotes the current relayer and the next-hop node. This approach ensures minimal routing control overhead and memory usage while maintaining compatibility with older firmware versions.

#### Stages of Establishing A Next-Hop
1. **Initial Transmission:** When a new message is directed to a single destination, it will use the managed flood approach.
2. **Acknowledgement or Response:** If a response (e.g., NodeInfo response, acknowledgment, or traceroute) is received and the relaying device matches one of the original relayers, it is designated as the next-hop.
3. **Subsequent Transmission:** Any future transmissions will use the designated next-hop node to relay the packet, reducing the number of devices involved in the process.


### 2. Meshtastic UI (MUI)
MUI is a brand-new interface for compatible standalone Meshtastic devices offering a seamless touchscreen experience, allowing users to interact with the network without needing a phone. MUI is still in early development, and Meshtastic is actively working on adding more features and improving performance.

**MUI is compatible the following devices:** LilyGo T-Deck, Seeed SenseCAP Indicator, unPhone, PICOmputer, T-HMI, Mesh-Tab,Raspberry Pi, LuckFox with TFT SPI and LoRa hat, or PC with Meshstick.

#### MUI Features
1. **Dashboard Screen:** Displays device status, new messages, detected nodes, date and time, radio settings, GPS, sound, Wi-Fi, and MQTT.
1. **Node List:** View, filter, and highlight nodes in your network.
1. **Chat Window:** Send and receive messages with persistent message history.
1. **Dynamic Position Map:** Pan and zoom with customizable map styles for better network visualization.
1. **Basic Device Configuration:** Quickly set up and adjust basic settings without the need for the Meshtastic app.
1. **Handy Tools:** Includes a mesh scanner, signal meter, traceroute, statistics, and packet log.
1. **Bluetooth Programming Mode:** Easily update and configure devices wirelessly using Bluetooth.
1. **Improved Device State File Management:** Meshtastic 2.6 introduces a more reliable way to handle device state and node data by separating them into distinct files. This change improves data integrity, reduces the risk of corruption, and makes recovery easier in the event of a filesystem issue or unexpected power loss.

### 3. Meshtastic over LAN (UDP)
Added support for messages to be sent over a local network (LAN) using UDP, currently available for ESP32 devices on WiFi. This feature allows nodes to communicate over a standard network connection, extending your mesh without relying solely on RF signals. This can be especially useful in locations with limited RF coverage or when bridging multiple Meshtastic networks over existing infrastructure.

### 4. Optimized LoRa Slot-Time Calculation
Meshtastic 2.6 includes improvements to LoRa slot-time calculations, making packet transmission more efficient. By reducing slot time, more slots become available within the same rebroadcast window, lowering the chance of packet collisions and improving overall network performance.


We have been testing the release on several devices for a few weeks, and encourage others to update to the latest firmware to take advantage of these new features. Meshtastic v2.6 represents a significant step forward in our mission to provide a robust and user-friendly mesh network.