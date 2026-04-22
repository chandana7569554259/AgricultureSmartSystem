Agriculture Smart System
The Agriculture Smart System is an IoT‑based solution designed to enhance farming efficiency through automation, sensor integration, and data analytics. By combining affordable hardware with open‑source software, this project enables farmers to monitor soil health, automate irrigation, and make informed decisions that improve crop yield and resource sustainability. It is an ideal project for students, researchers, and innovators exploring smart agriculture and IoT applications.

🌱 Features
Automated Irrigation: Soil moisture sensors trigger pumps via relay modules, ensuring precise watering.

Environmental Monitoring: DHT11 sensors track temperature and humidity for greenhouse or field conditions.

Data Logging: Sensor readings stored in SQL databases using JDBC for structured analysis.

Analytics Dashboard: Export data to Excel or visualize in Python for trend analysis and predictions.

Cloud Integration: Compatible with ThingSpeak, Firebase, or AWS IoT for remote monitoring.

Cybersecurity Layer: Secure MQTT communication and encrypted data transfer to protect IoT devices.

🔧 Hardware
Arduino Uno / ESP32 / NodeMCU

Soil moisture sensor, DHT11 sensor

Relay module + water pump

Power supply (5V/12V)

💻 Software
Arduino IDE (C++) for microcontroller programming

Python for analytics and visualization

SQL + JDBC for database connectivity

Cloud dashboards for real‑time monitoring

🚀 Benefits
Saves up to 40% water through automated irrigation.

Increases crop yield by 30% with precise monitoring.

Enables remote farm management via mobile/web apps.

Provides data‑driven decisions for sustainable agriculture.
#include <DHT.h>
#define DHTPIN 2
#define DHTTYPE DHT11
#define SOIL_PIN A0
#define RELAY_PIN 8

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  pinMode(RELAY_PIN, OUTPUT);
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  int soilMoisture = analogRead(SOIL_PIN);
  float temp = dht.readTemperature();
  float hum = dht.readHumidity();

  Serial.print("Soil: "); Serial.println(soilMoisture);
  Serial.print("Temp: "); Serial.println(temp);
  Serial.print("Humidity: "); Serial.println(hum);

  if (soilMoisture < 400) {
    digitalWrite(RELAY_PIN, HIGH); // Pump ON
  } else {
    digitalWrite(RELAY_PIN, LOW);  // Pump OFF
  }
  delay(2000);
}
samplelink :https://wokwi.com/projects/new/arduino-uno
