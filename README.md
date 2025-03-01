# Mesh Detect Flasher
<p align="center">
  <img src="https://raw.githubusercontent.com/lukeswitz/T-Halow/refs/heads/master/firmware/ColonelPanicWiFiRID/img/art_purps.svg" alt="T-Halow WiFi RID Image" width="100%" max-width="600px" />
</p>

**For the board by Colonel Panic:
[Tindie](https://www.tindie.com/products/colonel_panic/mesh-detect-2/)**

This script automates flashing different firmware to the Colonel Panic Mesh Detect board.

## Mesh Detect Firmwares

- [ESP32 OUI Sniffer](https://github.com/colonelpanichacks/esp32-oui-sniffer/tree/Xiao-esp32-c3-serial)
Alert when specific OUI(s) is seen by the Bluetooth scanner. Flash via Aurduino IDE. 
  - [Privacy Version](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect%20_privacy.ino) with preset OUIs

- [Deepwoods Device Detection](https://github.com/lukeswitz/deepwoods_device_detection/blob/Xiao-esp-32-c3/esp32c3_device_fingerprint.ino)
Scan WiFi and BT to form a baseline and alert to new devices. Flash via Aurduino IDE. 

- [WiFi Drone ID Detection FW](https://github.com/lukeswitz/T-Halow/tree/wifi_rid_mesh/firmware/firmware_Xiao_c3_Mesh_RID_Scanner_WiFi)
Sends drone detection messages include ID, RSSI, MAC, Operator ID, Location and more.


### Esptool Dependencies & Setup

```bash
# Install required packages
sudo apt-get update
sudo apt-get install -y git python3 python3-pip wget

# Install Python dependencies
pip3 install esptool pyserial
```

### Flashing 

```bash
# Download the script
wget https://raw.githubusercontent.com/lukeswitz/T-Halow/refs/heads/wifi_rid_mesh/firmware/firmware_Xiao_c3_Mesh_RID_Scanner_WiFi/flashDJI.sh

# Make executable
chmod +x flashDJI.sh
```
- Plug in your esp32

# Run the script
  ```
./flashDJI.sh
   ```
 
Follow the on-screen prompts. 
That’s it! The script will get your board flashed and running. 

> [!IMPORTANT]
> Power cycle the board after flashing to ensure no issues with the Heltec. 

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
