# WaterMeterKit V1

Hardware version V1 is based on the **ESP8266**.

## Specifications

| Component | Details |
|-----------|---------|
| **MCU** | ESP8266 |
| **Connectivity** | WiFi with Improv Serial |
| **Water Meter Interface** | Pulse meter sensor |
| **Sensors** | HDC1080 (Temp/Humidity) |
| **Status LED** | GPIO12 |
| **Green LED** | GPIO14 |
| **Blue LED** | GPIO16 |

## GPIO Pinout

| Function | GPIO |
|----------|------|
| Status LED | GPIO12 |
| Green LED | GPIO14 |
| Blue LED | GPIO16 |
| I2C SDA | GPIO4 |
| I2C SCL | GPIO5 |
| Pulse Meter | GPIO13 |

## Firmware Variants

| Variant | Description |
|---------|-------------|
| **watermeterkit.yaml** | Standard WiFi firmware with Improv |

## Installation via ESPHome Dashboard

```yaml
packages:
  watermeterkit: github://smarthomeshop/watermeterkit/watermeterkit-v1/watermeterkit.yaml@main
```

## Easy Setup

V1 supports easy WiFi setup via:
- **Captive Portal**: Connect to the `watermeterkit` hotspot and configure WiFi
- **Improv Serial**: Configure via USB connection

## OTA Updates

Firmware updates are automatically made available via:
- `https://smarthomeshop.github.io/watermeterkit/watermeterkit-v1-manifest.json`

Updates are directly available in Home Assistant when a new version is released.
