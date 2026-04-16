# WaterMeterKit V3

Hardware version V3 is based on the **ESP32-C6**.

## Specifications

| Component | Details |
|-----------|---------|
| **MCU** | ESP32-C6 |
| **Connectivity** | WiFi |
| **Water Meter Interface** | Pulse meter sensor |
| **Sensors** | HDC1080 (Temp/Humidity) |
| **Status LED** | GPIO1 |
| **Green LED** | GPIO0 |
| **Blue LED** | GPIO7 |
| **Flash** | 4MB |

## GPIO Pinout

| Function | GPIO |
|----------|------|
| Status LED | GPIO1 |
| Green LED | GPIO0 |
| Blue LED | GPIO7 |
| I2C SDA | GPIO5 |
| I2C SCL | GPIO4 |
| Pulse Meter | GPIO6 |

## Firmware Variants

| Variant | Description |
|---------|-------------|
| **watermeterkit.yaml** | Standard WiFi firmware for the ESP32-C6 hardware revision |

## Installation via ESPHome Dashboard

```yaml
packages:
  watermeterkit: github://smarthomeshop/watermeterkit/watermeterkit-v3/watermeterkit.yaml@main
```

## Notes

- OTA and API credentials are read from `secrets.yaml`.
- The fallback access point is named `WaterMeterKit-C6`.
- Required secrets for this package are `wifi_ssid`, `wifi_password`, `api_encryption_key`, `ota_password`, and `fallback_ap_password`.
