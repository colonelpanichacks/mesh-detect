<div align="center">

<pre>
   _____                .__      ________          __                 __   
  /     \   ____   _____|  |__   \______ \   _____/  |_  ____   _____/  |_ 
 /  \ /  \_/ __ \ /  ___/  |  \   |    |  \_/ __ \   __\/ __ \_/ ___\   __\
/    Y    \  ___/ \___ \|   Y  \  |    `   \  ___/|  | \  ___/\  \___|  |  
\____|__  /\___  >____  >___|  / /_______  /\___  >__|  \___  >\___  >__|  
        \/     \/     \/     \/          \/     \/          \/     \/      
</pre>

<img src="mesh.png" alt="hack the planet" width="75%" />

<p>text here aligns to the center of its box now!</p>

</div>
## Resources
*Hackster.io writeup/instructions  
[Mesh-Detect](https://www.hackster.io/colonelpanic/mesh-detect-549cbe)*

Mesh Detect board can be found on my Tindie Store:  
[mesh-detect board](https://www.tindie.com/products/colonel_panic/mesh-detect-2)

<a href="https://www.tindie.com/stores/colonel_panic/?ref=offsite_badges&utm_source=sellers_colonel_panic&utm_medium=badges&utm_campaign=badge_large">
    <img src="https://d2ss6ovg47m0r5.cloudfront.net/badges/tindie-larges.png" alt="I sell on Tindie" width="200" height="104">
</a>

## Mesh Detect Firmwares

- [Cam Sniffer](https://github.com/colonelpanichacks/esp32-oui-sniffer/tree/Xiao-esp32-c3-serial)  
  Alert when specific OUI(s) is seen by the Bluetooth scanner. Flash via Aurduino IDE.  
  - [Privacy Version](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect__privacy.ino) with preset OUIs

- [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection)  
  Scan WiFi and BT to form a baseline and alert to new devices. Flash via Aurduino IDE.

### Drone RemoteID to Mesh
- [BLE RemoteID to Mesh](https://github.com/colonelpanichacks/BLE-RemoteID)  
  Sends drone detection messages via Bluetooth Low Energy to the mesh network. Flash with Platformio

- [WiFi RemoteID to Mesh](https://github.com/colonelpanichacks/WiFi-RemoteID)  - This repo contains the dual core firmwares for esp32 c6, for both ble and wifi rid detection/decoding
  Sends drone detection messages via WiFi scanning to the mesh network. Flash with Platformio

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
- Make sure you are using the appropriate esp32 module outlined in each firmware documentation.

Credit: Firmware for RID and flasher based on work by cemaxecuter aka alphafox02. Modded with help of Colonel Panic.

- Original alphafox RID T-halow: https://github.com/alphafox02/T-Halow
- Thank you to Luke Switzer for the work on this project: https://github.com/lukeswitz/
