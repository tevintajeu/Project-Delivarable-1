# ICS 4111: Embedded Systems & IoT

## Semester Project – Deliverable 1: Automated Environmental and Gas Monitoring System for Carnation Cultivation

## Part 1: Environmental Requirements for Carnation Growth

Carnations require precise environmental control to ensure high-quality blooms and strong stems. The following table outlines the target metrics for our monitoring system:

| **Parameter**     | **Optimal Requirement / Range**     | **Technical Importance**                                                                                                               |
| ----------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Temperature       | Day: 18°C – 24°C Night: 10°C – 15°C | Prevents calyx splitting and ensures stem rigidity. Cool nights are required to prevent the plant from exhausting its energy reserves. |
| Relative Humidity | 60% – 75%                           | Prevents fungal diseases (rust/botrytis) and tip burn.                                                                                 |
| Soil Type         | Well-drained sandy loam             | Ensures aeration and prevents root rot.                                                                                                |
| Soil Moisture     | 60% – 65% (Field Capacity)          | Constant moisture is needed; avoid waterlogged or bone-dry soil.                                                                       |
| Soil pH           | 5.5 – 6.5                           | Slightly acidic soil is critical for optimal nutrient uptake.                                                                          |
| Sunlight Exposure | 12 – 13 hours (Photoperiod)         | Carnations are long-day plants; they need ample light for budding.                                                                     |

---

## Part 2: Hardware Inventory List

The following components will be used to prototype the automated system:

| **Component Name**         | **Quantity** | **Purpose**                                                    |
| -------------------------- | ------------ | -------------------------------------------------------------- |
| ESP32S DevKIT (30 Pin)     | 2            | Main microcontroller with Wi-Fi/Bluetooth for data processing. |
| DHT22 (AM2302) Sensor      | 1            | Measures ambient temperature and relative humidity.            |
| MQ-5 Gas Sensor            | 1            | Monitors LPG/Methane (used in greenhouse heating safety).      |
| 1.3" IIC OLED LCD (128x64) | 1            | Local visual display for real-time sensor readings.            |
| 5V 1-Channel Relay Module  | 1            | Controls high-voltage devices (fans/pumps) via a low trigger.  |
| Prototyping Breadboard     | 1            | Foundation for temporary circuit assembly.                     |
| Jumper Wires (M-M / M-F)   | 40           | Interconnects all modules and sensors.                         |

---

## Part 3: Component Datasheets

This section outlines the technical parameters and official documentation for the components selected for the Carnation Monitoring System. These specifications ensure electrical compatibility and guide the physical wiring of the embedded device.

| **Component**           | **Datasheet Reference Link**                                                                                                             | **Key Technical Specifications**                                                                                                                                                   |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ESP32S DevKIT (30-Pin)  | [ESP32S Series Reference](https://www.rfsolutions.co.uk/content/download-files/ESP32-S-DATASHEET.pdf)                                    | Operating Voltage: 3.3V. Features: Integrated Wi-Fi & Dual-mode Bluetooth. I/O: 30-pin configuration with capacitive touch, ADC, and DAC capabilities.                             |
| MQ-5 Gas Sensor         | [MQ-5 Gas Sensor PDF](https://www.scribd.com/document/7302233/MQ-5)                                                                      | Operating Voltage: 5V DC (required for internal heater). Target Gases: LPG, Methane, Butane. Output: Dual signal (Analog for concentration levels & Digital for threshold alerts). |
| DHT22 (AM2302) Sensor   | [DHT22 Technical Wiki](https://www.waveshare.com/wiki/DHT22_Temperature-Humidity_Sensor)                                                 | Operating Voltage: 3.3V – 5V. Signal Type: Digital single-bus. Precision: Humidity (2–5% accuracy); Temperature (<±0.5°C accuracy).                                                |
| 1.3" White IIC OLED LCD | [OLED Module Specs](https://www.rajguruelectronics.com/Product/4437/OLED%204%20PIN%20128x64%20display%20module%201.3%20inch%20white.pdf) | Resolution: 128x64 pixels. Communication: I2C Interface (SDA/SCL). Driver IC: Typically SSD1306 or SH1106.                                                                         |
| 1-Channel Relay Module  | [Relay Specifications](https://ktechnics.com/product/5v-1-channel/)                                                                      | Operating Voltage: 5V DC. Trigger Type: Low Level Trigger (activates when signal pin is pulled to GND). Capacity: Supports AC 250V/10A or DC 30V/10A.                              |

---

## Part 4: Schematic Diagrams

### Schematic A – 1 ESP32S connected to 1 MQ-5, 1 DHT22, and 1 LCD

![Schematic A – ESP32S + MQ-5 + DHT22 + LCD](SCH_Schematic1_2026-06-09.pdf)

### Schematic B – 1 ESP32S connected to 1 MQ-5 interfaced directly with another ESP32S connected to 1 DHT22

![Schematic B – ESP32S + MQ-5 ↔ ESP32S + DHT22](SCH_Schematic2_2026-06-09.pdf)

### Schematic C – 1 ESP32S connected to 1 DHT22 connected to 1 relay which is connected to another ESP32S connected to 1 MQ-5

![Schematic C – ESP32S + DHT22 + Relay ↔ ESP32S + MQ-5](SCH_Schematic3_2026-06-09.pdf)

---
