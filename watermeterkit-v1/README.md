# WaterMeterKit V1

Hardware version 1 of the WaterMeterKit, based on ESP8266.

## Specifications

| Specification | Value |
|--------------|-------|
| Chip | ESP8266 |
| Board | ESP01 1M |
| Network | WiFi only |
| Flash Size | 1MB |

## GPIO Pinout

| GPIO | Function |
|------|----------|
| GPIO4 | I2C SDA |
| GPIO5 | I2C SCL |
| GPIO12 | Status LED |
| GPIO13 | Pulse Meter (Water Flow) |
| GPIO14 | LED Green |
| GPIO16 | LED Blue |

## Sensors

| Sensor | Type | Interface |
|--------|------|-----------|
| Water Flow | Pulse Meter | GPIO13 |
| Temperature | HDC1080 | I2C |
| Humidity | HDC1080 | I2C |

## Firmware Variants

| File | Description |
|------|-------------|
| `watermeterkit-wifi.yaml` | Standard WiFi firmware |
| `watermeterkit-wifi-cloud.yaml` | WiFi + Cloud sync |

## File Structure

```
watermeterkit-v1/
├── base.yaml                      # Core configuration
├── wifi.yaml                      # WiFi network settings
├── cloud.yaml                     # Cloud sync module
├── watermeterkit-wifi.yaml        # Entry point: WiFi
├── watermeterkit-wifi-cloud.yaml  # Entry point: WiFi + Cloud
└── README.md                      # This file
```

## Building

```bash
# Create secrets.yaml
echo 'wifi_ssid: "YourSSID"' > secrets.yaml
echo 'wifi_password: "YourPassword"' >> secrets.yaml

# Build WiFi version
esphome compile watermeterkit-wifi.yaml

# Build WiFi Cloud version
esphome compile watermeterkit-wifi-cloud.yaml
```

## OTA Manifest URLs

| Variant | Manifest URL |
|---------|-------------|
| WiFi | `https://smarthomeshop.github.io/watermeterkit/watermeterkit-v1-wifi-manifest.json` |
| WiFi Cloud | `https://smarthomeshop.github.io/watermeterkit/watermeterkit-v1-wifi-cloud-manifest.json` |
