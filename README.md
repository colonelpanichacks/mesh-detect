# `MD Flasher`  

<p align="center">
  <img src="https://raw.githubusercontent.com/lukeswitz/WiFi-RemoteID/refs/heads/main/eyepurple.svg" alt="T-Halow WiFi RID Image" width="70%" />
</p>

## About  
- Easily flash different firmware onto the **Colonel Panic Mesh Detect Board.**
- An automatic `esptool.py` flasher, no IDE required.
- Options for S3, C6 and C3 Xiao ESP32 variants

---
           
✅ shasum: `d8d9686e430d3c4f3e0e2a94363194933d72e3b1`

# Flashing Firmware

> [!NOTE]
> - Latest Esptool is automatically downloaded to script directory if not on the sytem
> - Firmware binaries are replaced to ensure they're up-to-date.

## A. Linux & macOS

1. Download & Execute
```bash
# Install required packages (if needed)
sudo apt-get update
sudo apt-get install -y git python3 python3-pip wget
pip3 install esptool pyserial

# Download & run flasher
wget https://raw.githubusercontent.com/lukeswitz/mesh-detect/refs/heads/main/meshFlasher.sh

# Make executable & run
chmod +x meshFlasher.sh
./meshFlasher.sh
```

2. Plug in your **ESP32** via USB. Follow the on-screen prompts. Be sure to plug into the Xiao esp32 and not the Heltec USB.

## B. Windows (Powershell)

```powershell
# Ensure winget is available
if (-Not (Get-Command winget)) {
    Write-Warning "winget is not available. Please install it first."
    exit 1
}
```

```powershell
# Install required packages
winget install Gnu.Git
winget install Python.Python
winget install Python.Pip
```

```powershell
# Update pip and install Python modules
python -m pip install --upgrade pip
python -m pip install esptool pyserial
```

```powershell
# Download the script and verify its contents
$scriptUrl = "https://raw.githubusercontent.com/lukeswitz/mesh-detect/refs/heads/main/meshFlasher.sh"
$scriptPath = "meshFlasher.sh"

# Download the script
Invoke-WebRequest -Uri $scriptUrl -OutFile $scriptPath

# Optional: Verify the script contents before running it
# You can open the file in a text editor to inspect it
notepad $scriptPath
```

```powershell
# Run the script only if you trust it
Read-Host "Press Enter to run the script (Ctrl+C to cancel)"

# Set execution policy only for the current user and only if necessary
if ((Get-ExecutionPolicy -Scope CurrentUser) -ne "RemoteSigned") {
    Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force
}
```

2. Run the script
`.\meshFlasher.sh`


> [!IMPORTANT]
> Power cycle the board after flashing to ensure no issues with the Heltec. 

## Firmware Options  

### 🎥 1. OUI Sniffer  
- **[Official OUI FW](https://github.com/colonelpanichacks/esp32-oui-sniffer/tree/Xiao-esp32-c3-serial)**
- Detects specific **OUI(s)** via Bluetooth scanning.  
- Alerts when targeted OUIs are detected.  
- Flash via **Arduino IDE**.  

- 🔒 **[Privacy Sniffer](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect__privacy.ino)**
- Preset OUIs for Floc cameras, known snoops and other privacy invaders.
- Flash via `meshFlasher.sh`


### 2. 🌲 Deepwoods Device Detection  
- [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection)
- Scan WiFi and BT to form a baseline and alert to new devices.
- Detects and alerts on **new** devices.
- Flash via `meshFlasher.sh`

### 3. 🛸 Drone Remote ID to Meshtastic - BT and WiFi
*With Mesh-Mapper API 📡*

- [WiFi/BT Drone Remote id to Meshtastic](https://github.com/colonelpanichacks/WiFi-RemoteID)
  
- Sends drone detection messages with **ID, RSSI, MAC, Operator ID, Location**, and more.
- WebUI plots drones, pilots, looks up FAA IDs and more. Increase range using node-mode firmware on multiple devices. TAK, Serial and ZMQ support. 
- Flash via `meshFlasher.sh`


## Project Helpers

### Configuring Attached Mesh Node

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

## Resources
*Hackster.io writeup/instructions
[Mesh-Detect](https://www.hackster.io/colonelpanic/mesh-detect-549cbe)*

Mesh Detect board can be found on my Tindie Store:
[mesh-detect board](https://www.tindie.com/products/colonel_panic/mesh-detect-2)

<a href="https://www.tindie.com/stores/colonel_panic/?ref=offsite_badges&utm_source=sellers_colonel_panic&utm_medium=badges&utm_campaign=badge_large">
    <img src="https://d2ss6ovg47m0r5.cloudfront.net/badges/tindie-larges.png" alt="I sell on Tindie" width="200" height="104">
</a>


Credit: Firmware for RID and flasher based on work by cemaxecuter aka alphafox02. Modded with help of Colonel Panic. 

- Original alphafox RID T-halow: https://github.com/alphafox02/T-Halow
- Thank you to Luke Switzer for the work on this project: https://github.com/lukeswitz/
