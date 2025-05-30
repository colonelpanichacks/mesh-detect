<h1 align="center">Mesh Detect</h1>

<p align="center">
  <img src="https://raw.githubusercontent.com/lukeswitz/WiFi-RemoteID/refs/heads/main/eyepurple.svg" alt="T-Halow WiFi RID Image" width="70%" />
</p>


## Firmware Options

### 🎥 1. OUI Sniffer

* **[Official OUI FW](https://github.com/colonelpanichacks/esp32-oui-sniffer/tree/Xiao-esp32-c3-serial)**

* Detects specific **OUI(s)** via Bluetooth scanning.

* Alerts when targeted OUIs are detected.

* Flash via **Arduino IDE**.


### 2. 🌲 Deepwoods Device Detection

* [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection)
* Scan WiFi and BT to form a baseline and alert to new devices.
* Detects and alerts on **new** devices.
* Flash via `PlatformIO`

### 3. 🛸 Drone Remote ID to Meshtastic - BT and WiFi

*With Mesh-Mapper API 📡*

* [WiFi/BT Drone Remote id to Meshtastic](https://github.com/colonelpanichacks/WiFi-RemoteID)

* Sends drone detection messages with **ID, RSSI, MAC, Operator ID, Location**, and more.

* WebUI plots drones, pilots, looks up FAA IDs and more. Increase range using node-mode firmware on multiple devices. TAK, Serial and ZMQ support.

* Flash via `PlatformIO`

## 3D Prints
  
* **Mesh Detect SMA mount clip**
  SMA mount clip for the Mesh Destect board by OrdoOuroboros
  https://www.printables.com/model/1294183-mesh-detect-board-sma-mount

## Project Helpers

### Configuring Attached Mesh Node

* Official Docs [https://meshtastic.org/docs/configuration/module/serial/](https://meshtastic.org/docs/configuration/module/serial/)

#### Set the pcb mesh device to use serial mode, and configure the pins:

Ensure both the heltec and your receiver node are on the same channel. Set the pcb mesh settings to:

* Serial enabled
* 115200 baud rate
* Text message mode
* Pins defined RX/TX 19/20



## Troubleshooting

* If your esp32 is not being detected or giving any errors, hold the boot button and plug in the device.
* Make sure you are using a c3 esp32 module.

## Resources

*Hackster.io writeup/instructions*
[Mesh-Detect](https://www.hackster.io/colonelpanic/mesh-detect-549cbe)

Mesh Detect board can be found on my Tindie Store:
[mesh-detect board](https://www.tindie.com/products/colonel_panic/mesh-detect-2)

<a href="https://www.tindie.com/stores/colonel_panic/?ref=offsite_badges&utm_source=sellers_colonel_panic&utm_medium=badges&utm_campaign=badge_large">
    <img src="https://d2ss6ovg47m0r5.cloudfront.net/badges/tindie-larges.png" alt="I sell on Tindie" width="200" height="104">
</a>

Credit: Firmware for RID and flasher based on work by cemaxecuter aka alphafox02. Modded with help of Colonel Panic.

* Original alphafox RID T-halow: [https://github.com/alphafox02/T-Halow](https://github.com/alphafox02/T-Halow)
* Thank you to Luke Switzer for the work on this project: [https://github.com/lukeswitz/](https://github.com/lukeswitz/)
