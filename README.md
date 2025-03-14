# Mesh-Detect
<p align="center">
  <img src="https://raw.githubusercontent.com/lukeswitz/T-Halow/refs/heads/master/firmware/ColonelPanicWiFiRID/img/art_purps.svg" alt="T-Halow WiFi RID Image" width="100%" max-width="600px" />
</p>

## Resources
*Hackster.io writeup/instructions
[Mesh-Detect](https://www.hackster.io/colonelpanic/mesh-detect-549cbe)*


Mesh Detect board can be found on my Tindie Store:
[mesh-detect board](https://www.tindie.com/products/colonel_panic/mesh-detect-2)

<a href="https://www.tindie.com/stores/colonel_panic/?ref=offsite_badges&utm_source=sellers_colonel_panic&utm_medium=badges&utm_campaign=badge_large">
    <img src="https://d2ss6ovg47m0r5.cloudfront.net/badges/tindie-larges.png" alt="I sell on Tindie" width="200" height="104">
</a>



## Mesh Detect Firmwares

- [ESP32 OUI Sniffer](https://github.com/colonelpanichacks/esp32-oui-sniffer/tree/Xiao-esp32-c3-serial)
Alert when specific OUI(s) is seen by the Bluetooth scanner. Flash via Aurduino IDE. 
  - [Privacy Version](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect__privacy.ino) with preset OUIs

- [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection)
Scan WiFi and BT to form a baseline and alert to new devices. Flash via Aurduino IDE. 

- [Drone Remote id to Meshtastic](https://github.com/colonelpanichacks/wifi-rid-to-mesh)
Sends drone detection messages include ID, RSSI, MAC, Operator ID, Location and more.


## Configure Mesh Node

- Official Docs https://meshtastic.org/docs/configuration/module/serial/

#### Set the pcb mesh device to use serial mode, and configure the pins:

Ensure both the heltec and your receiver node are on the same channel. Set the pcb mesh settings to:
  - Serial enabled
  - 115200 baud rate
  - Text message mode
  - Pins defined RX/TX 19/20

![image](https://github.com/user-attachments/assets/1fee0617-447a-454c-ac78-10243ec7da5c)


## Troubleshooting

- If your esp32 is not being detected or giving any errors, hold the boot button and plug in the device.
- Make sure you are using a c3 esp32 module. 

Credit: Firmware for RID and flasher based on work by cemaxecuter aka alphafox02. Modded with help of Colonel Panic. 

- Original alphafox RID T-halow: https://github.com/alphafox02/T-Halow
- Thank you to Luke Switzer for the work on this project: https://github.com/lukeswitz/
