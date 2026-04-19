# Changelog

All notable customer-facing firmware changes for WaterMeterKit are tracked in this file.

This changelog starts on 2026-04-01. Earlier firmware versions existed before that date, but they were not tracked in a customer-facing changelog.

## [Unreleased]

- Add customer-facing changes here before the next release is published.
- Hardware naming has been corrected so the ESP8266-based WaterMeterKit is now published as V2.
- Initial WaterMeterKit V3 firmware track has been added for the ESP32-C6 hardware revision.
- WaterMeterKit V3 now includes Improv BLE, Improv Serial, and HTTP OTA update support for Made for ESPHome submission readiness.
- WaterMeterKit V3 now uses the product device name `watermeterkit` again and keeps captive portal / Improv onboarding aligned with the working CeilSense setup.
- WaterMeterKit V3 now routes serial logging and Improv Serial over `UART0` for boards that use the CP2102 USB-to-UART bridge.
- WaterMeterKit V3 has been simplified to a single WiFi-only configuration file; the separate `wifi.yaml` mixin and unused `default_network` substitution were removed.
- WaterMeterKit V1 and V2 now include a persistent `Water Meter Initial Value` setting and absolute `Water Meter Total` sensor that survive reboots and OTA updates.

## [WaterMeterKit V1 1.6] - 2026-04-01

### Added

- Customer-facing version history now lives in this repository.
- GitHub Releases will now be published for future firmware versions.

### Changed

- This file is now the public place for customer-facing firmware notes.
