# WaterMeterKit for Home Assistant / ESPHome

![WaterMeterKit](images/watermeterkit-product-shop.png)

WaterMeterKit is a compact water meter sensor designed to monitor your water consumption in real-time. It integrates seamlessly with Home Assistant via ESPHome and runs fully local (no cloud required).

## How it works

The WaterMeterKit uses a magnetic sensor to detect the rotating element on your analog water meter, counting each liter that passes through. Compatible with most major water meter brands including Actaris, Elster, Honeywell, Itron, Sensus and more.

👉 **Check compatibility for your water meter**: https://watermeterkit.nl/en

## Key features

- **Water flow monitoring**: Real-time water usage tracking with pulse meter sensor.
- **Environment sensing**: Temperature and humidity measurement.
- **Connectivity**: Wi-Fi with captive portal fallback.
- **Provisioning**: Improv Serial and captive portal for easy setup.
- **Local only**: Works also without cloud services (100% local); OTA supported via manifest on GitHub Pages.

## Variants

We publish firmware variants for different use cases. Each variant is a dedicated YAML in `watermeterkit-v1/` and ships with a matching Web Tools manifest on the `gh-pages` branch.

| Variant | Description |
|---------|-------------|
| WiFi | Standard WiFi connectivity |

## Getting started

1. **Hardware**: Install the WaterMeterKit on your water meter.
2. **Flash firmware**:
   - Use our web-based flash tool at https://smarthomeshop.io/en/firmware to flash or re-flash your kit.
   - Or compile/flash locally with ESPHome CLI.
3. **Onboarding**:
   - Connect to the `watermeterkit` hotspot if WiFi is not configured.
   - Use Improv Serial for provisioning via USB.

Please check for full documentation our quick start guide: https://smarthomeshop.io/quick-start-watermeterkit

## Repository layout

- `watermeterkit-v1/` — ESPHome configurations (base, wifi, and entry points)
- `.github/workflows/` — CI to build and publish artifacts/manifests to `gh-pages`
- `gh-pages` branch — public firmware and manifests (for OTA and ESP Web Tools)

## Sensors

| Sensor | Description |
|--------|-------------|
| Current Usage | Water flow rate in L/min |
| Total Consumption | Cumulative water usage in m³ |
| Temperature | Environment temperature |
| Humidity | Environment humidity |
| WiFi Signal | WiFi signal strength |
| Uptime | Device uptime |

## Contributing

PRs and issues are welcome. Please keep changes modular and follow ESPHome best practices.

## Support

- Product info and guides: https://watermeterkit.nl/en
- Store: https://smarthomeshop.io
- Community & support (Discord): https://smarthomeshop.io/discord

## License

This project is released under the CC BY‑NC 4.0 license


![WaterMeterKit](images/watermeterkit-inthebox-shop.png)