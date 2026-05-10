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

Hardware-first toolkit for surveillance detection and FAA Remote-ID drone tracking, with mesh-relayed alerts and a live web map.

**Hardware store — [colonelpanic.tech](https://colonelpanic.tech)**

</div>

---

## What's in this repo

A unified index for the **Mesh-Detect** hardware family — boards, firmwares, enclosures, and the companion web app. Everything links to the actual project repos; this README is the entry point.

| | |
|---|---|
| **Boards + kits** | [colonelpanic.tech](https://colonelpanic.tech) |
| **Build guide** | [Hackster.io](https://www.hackster.io/colonelpanic/mesh-detect-549cbe) |
| **Web app** | [drone-mesh-mapper](https://github.com/colonelpanichacks/drone-mesh-mapper) |
| **Author** | [@colonelpanichacks](https://github.com/colonelpanichacks) |

---

## Companion Web App — Drone Mesh Mapper

Live web map that ingests Remote-ID detections from Mesh-Detect boards over USB serial, plots drones + pilots in real time, overlays live ADS-B air traffic, and supports offline tile caching for field work with no internet.

[**colonelpanichacks/drone-mesh-mapper**](https://github.com/colonelpanichacks/drone-mesh-mapper)

| Capability | Detail |
|---|---|
| Real-time drone + pilot markers | Remote-ID broadcasts plotted live with dead-reckoning between updates |
| ADS-B air traffic overlay | adsb.lol, adsb.fi, airplanes.live, OpenSky, dump1090/readsb, Beast TCP |
| Offline maps | MBTiles cache, place search, configurable cache regions — fully usable off-grid |
| Geofencing | Polygon / circle / rectangle, per-fence color, drone or aircraft tag filters, per-fence webhooks |
| OSINT classification | Aircraft auto-classified (military / government / police / commercial / private); drones user-tagged |
| Exports | KML / CSV per session + cumulative history |
| Onboarding wizard | First-boot setup for USB ports, ADS-B source, default basemap, webhooks |
| One-line Pi install | `bash <(wget -qO- https://raw.githubusercontent.com/colonelpanichacks/drone-mesh-mapper/main/RPI/install_rpi.sh)` |

---

## Firmwares

### Surveillance Detection

| Firmware | What it does | Toolchain |
|---|---|---|
| [BLE/WiFi OUI Detection](https://github.com/colonelpanichacks/Esp32-oui-sniffer) | Configurable BLE + WiFi surveillance detection with web UI config portal. Mesh alerts via Meshtastic. | PlatformIO |
| [Deepwoods Device Detection](https://github.com/colonelpanichacks/deepwoods_device_detection) | Scans WiFi + BT to build a baseline, alerts when new devices appear. | Arduino IDE |
| [Privacy Version](https://github.com/lukeswitz/esp32-oui-sniffer/blob/Xiao-esp32-c3-serial/meshdetect__privacy.ino) | OUI sniffer with surveillance OUIs baked in (no user config). | Arduino IDE |

### Drone Remote-ID to Mesh

| Firmware | What it does | Toolchain |
|---|---|---|
| [Drone Mesh Mapper firmware](https://github.com/colonelpanichacks/drone-mesh-mapper) | Dual-core ESP32-S3 / ESP32-C5 / Heltec V3 firmware bundled with the web app. Remote detection node + home dedup/relay node, BLE + WiFi RID. | PlatformIO |

---

## Configure the Mesh Node

> [Meshtastic Serial Module Docs](https://meshtastic.org/docs/configuration/module/serial/)

Set the Heltec V3 (or any Meshtastic receiver node) to serial mode and match the pins. Both the detection node and the receiver must share the same Meshtastic channel.

| Setting | Value |
|---|---|
| Serial | **Enabled** |
| Baud Rate | **115200** |
| Mode | **TextMessage** |
| RX Pin | **19** |
| TX Pin | **20** |

![Meshtastic Serial Config](https://github.com/user-attachments/assets/1fee0617-447a-454c-ac78-10243ec7da5c)

---

## 3D Printable Enclosures

Official cases plus community-contributed designs:

| Model | Source | Designer |
|---|---|---|
| [Mesh-Detect Case](https://makerworld.com/en/models/1795881-mesh-detect-case) | MakerWorld | Colonel Panic |
| [Mesh-Detect Keychain](https://makerworld.com/en/models/1798841-mesh-detect-keychain) | MakerWorld | Colonel Panic |
| [Modular Mesh Detect Case](https://www.printables.com/model/1623378-modular-mesh-detect-case) | Printables | prestia (community) |
| [Mesh Detect Board SMA Mount](https://www.printables.com/model/1294183-mesh-detect-board-sma-mount) | Printables | Nitekry D Paul (community) |

Made an enclosure for Mesh-Detect? Open a PR adding it to this table.

---

## Troubleshooting

| Symptom | Fix |
|---|---|
| ESP32 not detected | Hold the **BOOT** button while plugging in the device. |
| Wrong board target | Confirm you're using the ESP32 module specified in the firmware's `platformio.ini`. |
| No mesh traffic | Check Meshtastic serial settings (above) and verify both nodes share the same channel + region. |
| Web map shows no aircraft | Toggle the ADS-B switch in the AIR TRAFFIC panel; first poll takes ~8s. |
| Tiles fail to cache | Verify network access; check the offline-mapping panel's job log for HTTP errors. |

---

## Credits

Remote-ID firmware originally based on work by [cemaxecuter / alphafox02](https://github.com/alphafox02/T-Halow). Thanks to [Luke Switzer](https://github.com/lukeswitz/) for ongoing contributions to this project.

3D enclosure designs by [Colonel Panic](https://makerworld.com/), [prestia](https://www.printables.com/model/1623378-modular-mesh-detect-case), and [Nitekry D Paul](https://www.printables.com/model/1294183-mesh-detect-board-sma-mount).

---

<div align="center">

**Hardware + kits → [colonelpanic.tech](https://colonelpanic.tech)**

</div>
