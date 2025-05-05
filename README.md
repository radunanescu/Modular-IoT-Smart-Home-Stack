# Modular-IoT-Smart-Home-Stack
A self-hosted smart home platform built with ESPHome, Home Assistant, and Docker. Includes MQTT communication, Zigbee lighting, custom automations, and ESP-based curtain, air, and boiler controls — all running on local hardware and designed to be modular and hackable.

---

## I. Overview

This project is a self-contained home automation system using:

- Home Assistant as the control hub
- Docker for service isolation (media, file sync, automation)
- ESP-based microcontrollers for physical sensors and actuators
- MQTT for real-time device communication
- Zigbee integration for lighting control
- Custom hardware (3D-printed and soldered) for enhanced functionality

---

## II. Features

1. Home Assistant running in Docker
2. Nextcloud and Jellyfin also containerized
3. ESPHome-powered devices:
   - Automated curtains (stepper motors + ESP32)
   - Boiler interlock safety system
   - Air quality monitors
   - Mistifiers triggered by local humidity
4. MQTT-based messaging across all devices
5. Zigbee2MQTT integration (IKEA Tradfri lighting)
6. Custom Raspberry Pi security system:
   - Camera stream
   - Magnetic door sensor
   - Alarm trigger and Home Assistant alert

---

## III. Tech Stack

- Docker and Docker Compose
- Home Assistant
- ESPHome (ESP32 and ESP8266)
- MQTT (via Mosquitto)
- Python (for custom automation logic)
- YAML (for configuration and automation)
- Zigbee (via Zigbee2MQTT)

---

## IV. System Architecture

`images/diagram.png`

- ESP devices send sensor data via MQTT
- Home Assistant listens and triggers responses
- Docker containers isolate services (Nextcloud, Jellyfin, HA)
- Raspberry Pi handles local camera and door sensors
- Zigbee devices integrated through a USB stick and MQTT bridge

---

## V. How to Use

1. Clone the repository
2. Install Docker and Docker Compose
3. Set up MQTT broker (Mosquitto)
4. Flash ESP devices using configs in the `/esphome` directory
5. Start Home Assistant with the `/home-assistant` configuration
6. Customize to match your hardware layout and preferences

---

## VI. Hardware Used

- Raspberry Pi 3 – handles alarm system and camera stream
- ESP32 and ESP8266 microcontrollers – for custom sensors and actuators
- Zigbee USB dongle – for IKEA Tradfri and Zigbee2MQTT integration
- IKEA Tradfri lights and buttons
- 3D printed components – curtain motor mounts, sensor enclosures
- Custom relay boards – for boiler control and mistifier automation
- Home server:
  - AMD Ryzen 1600X
  - NVIDIA GTX 960 GPU
  - 2 × 1 Gbps Ethernet ports (bonded via LACP)
  - Connected to Ubiquiti 1 Gbps managed switch

---

## VII. Planned Improvements

- Grafana dashboard for real-time data visualization
- WireGuard or ZeroTier VPN for secure remote access
- Voice assistant integration (e.g. Mycroft or offline Whisper-based control)
- Auto-backup system for configurations and logs

---

## VIII. Notes

This project is experimental and constantly evolving. Designed for hands-on learning, privacy, and control. Open to suggestions or collaboration.
