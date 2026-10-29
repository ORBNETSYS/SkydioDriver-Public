# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),

# Skydio Driver for XProtect

## [1.0.1] = 29.10.2026

> **⚠ Important — before installing:**
> - Install the **Skydio Plugin** on every computer running the **XProtect Management Client**, **XProtect Event Server** or **XProtect Smart Client**, and use the same version everywhere.
> - The **Skydio Smart Client plugin** needs additional **Skydio Cloud** API token permissions (**Missions**, **Mission Schedule**, **Mission Controls**, **Dock**, **Alerts**, **Media**). See **Skydio Cloud & API Token Permissions**.

### Added
* **Skydio Dashboard:** a dedicated **Skydio Dashboard** tab in the **XProtect Smart Client**, with a searchable drone list, the selected drone bar and tabs for **Overview**, **Mission Library**, **Scheduled Missions**, **Mission History**, **Drone Media**, **Skydio Alerts** and **Command History**.
* **ORBNET Skydio Plugin side panel:**
  * **Fleet Status** with **Total Drones**, **Online**, **Offline** and **Live Drones**.
  * **Selected Drone** details, with **Dock Details** (dock status, **Copy Position**, **Show Address**).
  * **Drone Mission Commands**: **Run mission**, **Pause mission**, **Resume mission**, **Land Outside the Dock**, **Return & Land in Dock** and **Skip to Waypoint**, each with a confirmation before it is sent.
  * **Drone Files & Events**: **Skydio Alerts**, **Skydio Drone Media** (with filters and download) and **Skydio Command History**.
  * **Recent Activity** and **Diagnostics**.
* **Live Telemetry:** **Altitude**, **Height above launch**, **Height above ground**, **Heading**, **Mission** progress and **Camera looking at**, with a description on each row name, and **Updated** / **No telemetry since** status.
* **Copy Drone Pos.**, **Drone Address**, **Copy Target Pos.** and **Target Address** buttons; the address window allows copying its text.
* **Pop Out Live Video** window with the drone's color and thermal cameras (**View**: Both, Color, Thermal), which stays live when the **XProtect Smart Client** switches to playback.
* **Auto refresh** of the fleet and the selected drone, shared between the side panel and the **Skydio Dashboard**.
* Double-click a table row to copy it.
* **Skydio events for XProtect rules and alarms:** **ORBNET Skydio - Drone launched** and **ORBNET Skydio - Battery below threshold**, created automatically, with settings in `skydio-rule-events.json`.
* The driver's live telemetry now includes altitude, heading, heights above launch and ground, mission progress and the camera target.

### Fixed
* Live telemetry reconnecting continuously.
* Live telemetry stopping until the hardware was restarted when the **Skydio Cloud** connection dropped without a close message.
* Live telemetry connection waiting indefinitely when **Skydio Cloud** did not answer (10 seconds connection limit, reconnect after 15 seconds without data).
* **XProtect Smart Client** crash when the selected drone was running a mission whose template was not loaded.
* Skydio events not created when the **XProtect Management Server** was not reachable when the **XProtect Event Server** started.

## [1.0.0] - 19.10.2026

### Added
* **Skydio Smart Client plugin**: Skydio fleet and drone information in the **XProtect Smart Client**, with mission controls for the selected drone.
* **XProtect Event Server** plugin handling the **XProtect Smart Client** requests to **Skydio Cloud**.

## [0.9.0] - 22.05.2025

### Added
* **Skydio Driver** for the **XProtect Recording Server**: one hardware device per drone, with a **Color Camera** and a **Thermal Camera** video channel (RTSPS) and a **Telemetry** metadata channel.
* **Skydio Fleet Hub** in the **XProtect Management Client**:
  * **Driver Manager**: fetch the drones from **Skydio Cloud** with an API token, set a default **XProtect Recording Server** and create drivers for the selected drones.
  * **License Manager**: apply and revoke driver licenses, export a license request and import a license.
* Free **30-day trial** with up to 10 video channels.
* Live telemetry for **ORBNET Live Maps**.
