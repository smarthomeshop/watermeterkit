# WaterMeterKit V3

Hardware version V3 is based on the **ESP32-C6**.

## Specifications

| Component | Details |
|-----------|---------|
| **MCU** | ESP32-C6 |
| **Connectivity** | WiFi + Bluetooth LE |
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
| **watermeterkit-cloud.yaml** | WiFi firmware with SmartHomeShop Cloud support |
| **watermeterkit-thread.yaml** | Local Thread firmware for an existing Thread network |

## Installation via ESPHome Dashboard

```yaml
packages:
  watermeterkit: github://smarthomeshop/watermeterkit/watermeterkit-v3/watermeterkit.yaml@main
```

## Notes

- Initial onboarding is handled through captive portal, Improv BLE, or Improv Serial.
- HTTP OTA updates are exposed through the firmware update entity.
- The fallback access point uses the device name as SSID and password.

## Thread Firmware

The Thread variant is local-only. It joins your existing Thread network through a Thread border router and connects directly to Home Assistant over IPv6. It does not use WiFi, the SmartHomeShop Cloud, or a fallback hotspot.

Before installing, copy the **Active dataset TLVs** from Home Assistant under Settings -> Devices & Services -> Thread -> Configure. Create an ESPHome device with:

```yaml
substitutions:
  thread_dataset: "PASTE_YOUR_ACTIVE_DATASET_TLVS_HERE"

packages:
  remote_package:
    url: https://github.com/smarthomeshop/watermeterkit
    ref: main
    files: [watermeterkit-v3/watermeterkit-thread.yaml]
    refresh: 1d
```

Replace the placeholder with your dataset TLVs and flash the first installation over USB. After boot, Home Assistant should discover the device through ESPHome over Thread. Thread firmware updates are done through ESPHome Dashboard over IPv6 or USB.
