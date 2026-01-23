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

Firmware updates are done via the ESPHome Dashboard in Home Assistant:
1. Go to Settings → Add-ons → ESPHome
2. Your WaterMeterKit will show when an update is available
3. Click "Update" to flash the new firmware wirelessly

**Note:** Due to ESP8266 1MB flash limitations, HTTP-based OTA is not supported. Updates must be done via ESPHome Dashboard or USB.

For initial flashing or recovery, use our web-based flash tool:
- https://smarthomeshop.io/en/firmware
