# IoT-Agriculture-Monitoring-System
This IoT-based system monitors soil moisture, temperature, humidity, and light intensity. When moisture drops below a set threshold, it automatically activates a solenoid valve to water the plants. A vibration sensor detects movement or disturbances from animals or rodents around the plantation. The solution is suitable for indoor plants, greenhouses, and regular farming, and uses the Adafruit IoT platform for real-time online monitoring.


# Circuit and working
The system uses a NodeMCU ESP8266/ESP-32 as the core controller to collect data from multiple sensors and transmit it over Wi-Fi. It monitors four soil moisture sensors, an LDR for light intensity, a vibration sensor, and a DHT11 temperature–humidity sensor.

When soil moisture or humidity drops below a programmed threshold, the NodeMCU activates a water solenoid valve via a relay. The LDR detects day/night conditions; if light intensity is low (especially at night), the system turns on a room light through the relay. The vibration sensor detects disturbances near the plants and alerts the user through the NodeMCU’s onboard LED.

Since the NodeMCU has only one analog input, a 16×1 multiplexer (74HC4067) is used to read five analog sensors. The NodeMCU selects each sensor input using control pins (D0–D3), and the multiplexer’s output is fed into A0. The controller processes all sensor data, controls the relay outputs (D5, D7), and sends real-time updates to the Adafruit IoT platform.
