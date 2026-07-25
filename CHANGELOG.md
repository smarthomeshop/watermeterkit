# Changelog

All notable customer-facing firmware changes for WaterMeterKit are tracked in this file.

This changelog starts on 2026-04-01. Earlier firmware versions existed before that date, but they were not tracked in a customer-facing changelog.

## [Unreleased]

- Fixed V3 firmware installation failures after an ESPHome dashboard import added API encryption; encrypted local and cloud builds now fit the existing OTA partitions again.

## [WaterMeterKit V1 1.9] - 2026-07-17


- Fixed WaterMeterKit V1 and V2 cloud firmware restarting every 15 minutes when Home Assistant is not connected, matching the earlier V3 fix.



## [WaterMeterKit V2 1.10] - 2026-07-17


- Fixed WaterMeterKit V1 and V2 cloud firmware restarting every 15 minutes when Home Assistant is not connected, matching the earlier V3 fix.



## [WaterMeterKit V3 2.9] - 2026-07-17


- Added a CPU temperature diagnostic sensor, also synced to SmartHomeShop Cloud, and updated the built-in web interface to version 3.



## [WaterMeterKit V3 2.8] - 2026-07-17


- Fixed cloud firmware restarting every 15 minutes when Home Assistant is not connected: the no-client reboot of the native API is now disabled on cloud firmware, so cloud-only setups run uninterrupted.



## [WaterMeterKit V1 1.8] - 2026-07-13


- Added local Thread firmware for WaterMeterKit V3, plus separate WiFi and SmartHomeShop Cloud package variants.
- All WaterMeterKit hardware versions now use the ESPHome web server version 3 interface.


## [WaterMeterKit V2 1.9] - 2026-07-13


- Added local Thread firmware for WaterMeterKit V3, plus separate WiFi and SmartHomeShop Cloud package variants.
- All WaterMeterKit hardware versions now use the ESPHome web server version 3 interface.


## [WaterMeterKit V3 2.7] - 2026-07-13


- Added local Thread firmware for WaterMeterKit V3, plus separate WiFi and SmartHomeShop Cloud package variants.
- All WaterMeterKit hardware versions now use the ESPHome web server version 3 interface.


## [WaterMeterKit V3 2.6] - 2026-04-19


- Hardware naming has been corrected so the ESP8266-based WaterMeterKit is now published as V2.
- Initial WaterMeterKit V3 firmware track has been added for the ESP32-C6 hardware revision.
- WaterMeterKit V3 now includes Improv BLE, Improv Serial, and HTTP OTA update support for Made for ESPHome submission readiness.
- WaterMeterKit V3 now uses the product device name `watermeterkit` again and keeps captive portal / Improv onboarding aligned with the working CeilSense setup.
- WaterMeterKit V3 now routes serial logging and Improv Serial over `UART0` for boards that use the CP2102 USB-to-UART bridge.
- WaterMeterKit V3 keeps its WiFi network configuration in a separate package so the same base can also be reused by the local Thread firmware.
- WaterMeterKit V3 now also includes `Water Meter Initial Value` and the persistent absolute `Water Meter Total` sensor, matching the V1/V2 behavior.
- WaterMeterKit V3 now includes local WiFi, SmartHomeShop Cloud, and Thread firmware packages. Thread uses the user's own Active dataset and is installed through ESPHome over USB.
- WaterMeterKit V1 and V2 now include a persistent `Water Meter Initial Value` setting and absolute `Water Meter Total` sensor that survive reboots and OTA updates.


## [WaterMeterKit V1 1.6] - 2026-04-01

### Added

- Customer-facing version history now lives in this repository.
- GitHub Releases will now be published for future firmware versions.

### Changed

- This file is now the public place for customer-facing firmware notes.
