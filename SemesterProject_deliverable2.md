## a. 1 ESP32S connected to 1 MQ-5, 1 DHT22 and 1 LCD (both physical and simulated models are expected)

Wokwi link: https://wokwi.com/projects/468251053125185537

**Simulated:**

![](image1.jpeg)

**Physical:**

![](image2.jpeg)

**Arduino IDE Output:**

## b. 1 ESP32S connected to 1 MQ-5 interfaced directly with another ESP32S connected to 1 DHT22 [develop EITHER a physical or simulated model – interchangeable with architecture (c)]

Wokwi link: https://wokwi.com/projects/468412461036174337

**Physical:**

![](image3.jpeg)
![](image4.jpeg)

## c. 1 ESP32S connected to 1 DHT22 connected to 1 relay which is connected to another ESP32S connected to 1 MQ-5 [develop EITHER a physical or simulated model – interchangeable with architecture (b)]

Wokwi link: https://wokwi.com/projects/468330427356796929

**Physical:**

![](image5.jpeg)

## Technical Issues

| No. | Issue | Recommendation |
|---|---|---|
| 1 | In the Wokwi simulation for architecture (b), the display screen showed nothing even though the rest of the setup worked fine. | Double-check that the screen is connected to the correct pins and set up the same way the simulator expects; test the screen on its own first before adding it to the full circuit. |
| 2 | The physical display screens didn't show anything either. This happened with two different screens we tried. | Check the screen's brightness/contrast adjustment, make sure it's getting the right power connection, and confirm it's properly detected by the ESP32. |
