<div align="center">

<pre>
   _____                .__      ________          __                 __
  /     \   ____   _____|  |__   \______ \   _____/  |_  ____   _____/  |_
 /  \ /  \_/ __ \ /  ___/  |  \   |    |  \_/ __ \   __\/ __ \_/ ___\   __\
/    Y    \  ___/ \___ \|   Y  \  |    `   \  ___/|  | \  ___/\  \___|  |
\____|__  /\___  >____  >___|  / /_______  /\___  >__|  \___  >\___  >__|
        \/     \/     \/     \/          \/     \/          \/     \/      </pre>

<img src="mesh.png" alt="Mesh-Detect" width="50%" />

### ESP32-S3 + Meshtastic LoRa detection platform

</div>

---

## Get the Hardware

| Where | What |
|---|---|
| [colonelpanic.tech](https://colonelpanic.tech) | Full kits, PCBs, pre-flashed boards |
| [Hackster.io build guide](https://www.hackster.io/colonelpanic/mesh-detect-549cbe) | DIY assembly |

---

## Web Flasher

Plug the board in, open the page in Chrome, Edge, or Opera, hit Flash. No PlatformIO needed.

[colonelpanichacks.github.io/drone-mesh-mapper/flasher/](https://colonelpanichacks.github.io/drone-mesh-mapper/flasher/)

Three builds available in one page:

- **Standard Dualcore** - single detector board, BLE + WiFi Remote-ID over UART to a Heltec V3
- **Node Mode / Remote** - field detector, tags detections with a per-board node_id
- **Node Mode / Home** - base bridge, dedups multi-node hits by drone MAC, forwards to `mesh-mapper.py`

---

## Firmwares

### Drone Remote-ID to Mesh

| Firmware | Notes | Toolchain |
|---|---|---|
| [Drone Mesh Mapper](https://github.com/colonelpanichacks/drone-mesh-mapper) | Dual-core ESP32-S3 / ESP32-C5. BLE + WiFi RID, mesh relay, dedup for multi-node deployments. Bundled with a Flask + Leaflet web app. | [Web Flasher](https://colonelpanichacks.github.io/drone-mesh-mapper/flasher/) or PlatformIO |
| [BLE RemoteID to Mesh](https://github.com/colonelpanichacks/BLE-RemoteID) | BLE-only variant, drone detections over Meshtastic. | PlatformIO |
| [WiFi RemoteID to Mesh](https://github.com/colonelpanichacks/WiFi-RemoteID) | ESP32-C6 dual-core firmwares, both BLE and WiFi RID. | PlatformIO |

### Surveillance Detection

| Firmware | Notes | Toolchain |
|---|---|---|
| [BLE/WiFi OUI Detection](https://github.com/colonelpanichacks/Esp32-oui-sniffer) | Configurable BLE + WiFi surveillance detection. Web UI config portal. Mesh alerts. | PlatformIO |
| [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection) | Baselines local WiFi + BT, alerts on new devices. | Arduino IDE |
| [Privacy Version](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect__privacy.ino) | OUI sniffer with surveillance OUIs baked in, no config. | Arduino IDE |

---

## Configure the Mesh Node

The Heltec V3 (or any Meshtastic receiver) has to run its Serial Module in TEXTMSG mode so it can relay Remote-ID JSON over LoRa. Both ends must share the same Meshtastic channel and region.

| Setting | Value |
|---|---|
| `serial.enabled` | true |
| `serial.mode` | TEXTMSG |
| `serial.baud` | BAUD_115200 |
| `serial.rxd` | 19 |
| `serial.txd` | 20 |

Docs: [meshtastic.org/docs/configuration/module/serial](https://meshtastic.org/docs/configuration/module/serial/)

![Meshtastic Serial Config](https://github.com/user-attachments/assets/1fee0617-447a-454c-ac78-10243ec7da5c)

---

## 3D Printable Enclosures

| Model | Source | Designer |
|---|---|---|
| [Mesh-Detect Case](https://makerworld.com/en/models/1795881-mesh-detect-case) | MakerWorld | Colonel Panic |
| [Mesh-Detect Keychain](https://makerworld.com/en/models/1798841-mesh-detect-keychain) | MakerWorld | Colonel Panic |
| [Modular Mesh-Detect Case](https://www.printables.com/model/1623378-modular-mesh-detect-case) | Printables | prestia |
| [SMA Mount](https://www.printables.com/model/1294183-mesh-detect-board-sma-mount) | Printables | Nitekry D Paul |

Made an enclosure? PR to add it.

---

## Troubleshooting

| Symptom | Fix |
|---|---|
| Board not detected | Hold **BOOT** while plugging in. |
| Wrong board target | Check the firmware's `platformio.ini` for the exact ESP32 module. |
| No mesh traffic | Verify Meshtastic serial settings above and that both nodes share the same channel + region. |

---

## Credits

Remote-ID firmware based on work by [cemaxecuter / alphafox02](https://github.com/alphafox02/T-Halow). Thanks to [Luke Switzer](https://github.com/lukeswitz/) for ongoing contributions.

Enclosures by Colonel Panic, [prestia](https://www.printables.com/model/1623378-modular-mesh-detect-case), and [Nitekry D Paul](https://www.printables.com/model/1294183-mesh-detect-board-sma-mount).

## License

MIT, see [LICENSE](LICENSE).
