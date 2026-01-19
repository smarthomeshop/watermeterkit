# WaterMeterKit for Home Assistant

![WaterMeterKit Logo](images/watermeterkit-logo.png)

The WaterMeterKit is a versatile and comprehensive solution for monitoring water consumption in your home through Home Assistant. This kit provides real-time insights into your water usage and allows you to track trends over time. It's a perfect addition for those who want to become more aware of their water consumption and make informed decisions about water usage.

Check our website to view if your watermeter is compatible: https://watermeterkit.nl/en

## Features

- **Real-time Monitoring:** Get real-time data on your water consumption, including water flow rate and environment temperature.

- **Data Visualization:** Visualize your water usage trends per hour, day, month, or year in liters, right within Home Assistant.

- **Environment Monitoring:** The kit also measures the temperature and humidity of the space where your water meter is located.

- **Easy Installation:** The WaterMeterKit is designed for easy installation on your existing water supply line.

- **Integration with Home Assistant:** Seamlessly integrate the kit with Home Assistant using the provided blueprints.

- **OTA Updates:** Automatic firmware updates via GitHub Pages with easy firmware type switching.

- **Cloud Sync (Optional):** Sync your water usage data to the SmartHomeShop cloud for advanced analytics.

## Hardware Versions

| Version | Chip | Network | Cloud | Status |
|---------|------|---------|-------|--------|
| V1 | ESP8266 | WiFi | ✅ | Current |

## Firmware Variants

Each hardware version has multiple firmware variants available:

| Variant | Description |
|---------|-------------|
| WiFi | Standard WiFi connectivity |
| WiFi Cloud | WiFi + Cloud sync to SmartHomeShop |

## Repository Structure

```
watermeterkit/
├── .github/
│   └── workflows/
│       ├── esphome-build.yml      # Reusable build workflow
│       └── publish.yml            # Main workflow (triggers builds)
├── watermeterkit-v1/              # Hardware version 1 (ESP8266)
│   ├── base.yaml                  # Core functionality
│   ├── wifi.yaml                  # WiFi network configuration
│   ├── cloud.yaml                 # Cloud sync (optional)
│   ├── watermeterkit-wifi.yaml    # Main: base + wifi
│   └── watermeterkit-wifi-cloud.yaml  # Main: base + wifi + cloud
├── images/
│   └── watermeterkit-logo.png
└── README.md
```

## Installation

### Option 1: Web Installer (Recommended)

Visit our web installer at [SmartHomeShop.io](https://smarthomeshop.io) to flash the firmware directly from your browser.

### Option 2: ESPHome Dashboard

Add the following to your ESPHome configuration:

```yaml
# For WiFi version:
packages:
  watermeterkit: github://smarthomeshop/watermeterkit/watermeterkit-v1/watermeterkit-wifi.yaml@main

# For WiFi Cloud version:
packages:
  watermeterkit: github://smarthomeshop/watermeterkit/watermeterkit-v1/watermeterkit-wifi-cloud.yaml@main
```

### Option 3: Manual Build

1. Clone this repository
2. Create a `secrets.yaml` file in the version folder with your WiFi credentials:
   ```yaml
   wifi_ssid: "YourSSID"
   wifi_password: "YourPassword"
   ```
3. Build with ESPHome: `esphome run watermeterkit-v1/watermeterkit-wifi.yaml`

## OTA Updates

The WaterMeterKit supports Over-The-Air updates via HTTP request. You can switch between firmware variants (WiFi/WiFi Cloud) directly from Home Assistant:

1. Go to your WaterMeterKit device in Home Assistant
2. Find the "Firmware Type" selector
3. Choose your preferred variant
4. The firmware update entity will check for updates from the correct manifest

Firmware binaries are automatically published to GitHub Pages on every release.

## Contents of the Kit

- WaterMeterKit (ESP8266)
- All necessary cables and watermeter sensor
- Installation guide

## Sensors

| Sensor | Description |
|--------|-------------|
| Current Usage | Water flow rate in L/min |
| Total Consumption | Cumulative water usage in m³ |
| Temperature | Environment temperature (HDC1080) |
| Humidity | Environment humidity (HDC1080) |
| WiFi Signal | WiFi signal strength |
| Uptime | Device uptime |

## Contributing

Contributions are welcome! If you'd like to contribute to the project, please make a PR.

## Support

For any questions or issues, please visit our [Discord community](https://smarthomeshop.io/discord) where you can find help and connect with other users.

## License

This project is licensed under the [MIT License](LICENSE).
