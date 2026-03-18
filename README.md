<div align="center">

<pre>
   _____                .__      ________          __                 __
  /     \   ____   _____|  |__   \______ \   _____/  |_  ____   _____/  |_
 /  \ /  \_/ __ \ /  ___/  |  \   |    |  \_/ __ \   __\/ __ \_/ ___\   __\
/    Y    \  ___/ \___ \|   Y  \  |    `   \  ___/|  | \  ___/\  \___|  |
\____|__  /\___  >____  >___|  / /_______  /\___  >__|  \___  >\___  >__|
        \/     \/     \/     \/          \/     \/          \/     \/      </pre>

<img src="mesh.png" alt="hack the planet" width="50%" />

**ESP32-S3 + Meshtastic LoRa detection platform**

[![Tindie](https://d2ss6ovg47m0r5.cloudfront.net/badges/tindie-larges.png)](https://www.tindie.com/stores/colonel_panic/?ref=offsite_badges&utm_source=sellers_colonel_panic&utm_medium=badges&utm_campaign=badge_large)

</div>

---

## Get the Hardware

| | Link |
|---|---|
| **Mesh-Detect v2 Board** | [Tindie Store](https://www.tindie.com/products/colonel_panic/mesh-detect-2) |
| **PCB Only** | [Tindie Store](https://www.tindie.com/products/colonel_panic/mesh-detect-pcb-only/) |
| **Build Guide** | [Hackster.io](https://www.hackster.io/colonelpanic/mesh-detect-549cbe) |

---

## Firmwares

### Surveillance Detection
| Firmware | Description | Flash With |
|----------|-------------|------------|
| [BLE/WiFi OUI Detection](https://github.com/colonelpanichacks/Esp32-oui-sniffer) | Configurable BLE + WiFi surveillance detection with web UI config portal. Sends alerts over Meshtastic mesh. | PlatformIO |
| [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection) | Scan WiFi and BT to form a baseline and alert to new devices. | Arduino IDE |
| [Privacy Version](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect__privacy.ino) | OUI sniffer with preset surveillance OUIs baked in. | Arduino IDE |

### Drone Remote ID to Mesh
| Firmware | Description | Flash With |
|----------|-------------|------------|
| [BLE RemoteID to Mesh](https://github.com/colonelpanichacks/BLE-RemoteID) | Drone detection via Bluetooth Low Energy, alerts sent to mesh network. | PlatformIO |
| [WiFi RemoteID to Mesh](https://github.com/colonelpanichacks/WiFi-RemoteID) | Drone detection via WiFi scanning. Dual core firmwares for ESP32-C6, supports both BLE and WiFi RID. | PlatformIO |

---

## 3D Printable Enclosures

| Model | Link |
|-------|------|
| **Mesh-Detect Case** | [MakerWorld](https://makerworld.com/en/models/1795881-mesh-detect-case) |
| **Mesh-Detect Keychain** | [MakerWorld](https://makerworld.com/en/models/1798841-mesh-detect-keychain) |
| **SMA Mount Clip** | [Printables](https://www.printables.com/model/1294183-mesh-detect-board-sma-mount) |

---

## Configure Mesh Node

> [Meshtastic Serial Module Docs](https://meshtastic.org/docs/configuration/module/serial/)

Set the PCB mesh device to use serial mode and configure the pins. Ensure both the Heltec and your receiver node are on the same channel.

| Setting | Value |
|---------|-------|
| Serial | **Enabled** |
| Baud Rate | **115200** |
| Mode | **TextMessage** |
| RX Pin | **19** |
| TX Pin | **20** |

![Meshtastic Serial Config](https://github.com/user-attachments/assets/1fee0617-447a-454c-ac78-10243ec7da5c)

---

## Troubleshooting

- **ESP32 not detected?** Hold the BOOT button while plugging in the device.
- **Wrong board?** Make sure you are using the appropriate ESP32 module outlined in each firmware's documentation.

---

## Credits

RID firmware based on work by [cemaxecuter / alphafox02](https://github.com/alphafox02/T-Halow). Thank you to [Luke Switzer](https://github.com/lukeswitz/) for contributions to this project.
