🌲🔥 FLAME GUARD
Smart IoT-Based Forest Fire Detection and Prevention System
1️⃣ Introduction
Forest fires are one of the most dangerous natural disasters. Every year, thousands of trees, animals, and even villages are destroyed due to uncontrolled fires. In countries like India, forest fires increase during summer because of high temperature and dry climate.
The main problem is late detection. By the time people notice the fire, it spreads rapidly.
To solve this problem, we introduce FLAME GUARD — a Smart IoT-based Forest Fire Detection and Automatic Prevention System.
2️⃣ Problem Statement
Forest fires spread very fast.
Manual monitoring is difficult in large forests.
Delay in communication causes heavy damage.
Lack of automatic emergency response system.
Villages near forests are not warned early.
There is a need for an automatic, fast, and intelligent fire detection system.
3️⃣ Proposed Solution – FLAME GUARD
FLAME GUARD is an automated smart system that:
Detects fire using flame and smoke sensors.
Cuts local electricity supply in affected zone.
Sends emergency alert message to fire office.
Activates alarm in nearby villages and cities.
Automatically starts underground water sprinklers.
Works with IoT technology for real-time monitoring.
4️⃣ Components Used
🔥 Flame Sensor
💨 Smoke Sensor
🧠 Microcontroller (Arduino / ESP8266)
📡 GSM Module (for SMS alert)
📱 IoT Platform (like Blynk)
💧 Water Pump
🚿 Sprinkler System
🔔 Buzzer Alarm
⚡ Relay Module (to cut power supply)
☀️ Solar Panel (Backup Power)
5️⃣ Working Principle
Step 1: Detection
When fire starts, the flame sensor detects infrared radiation and the smoke sensor detects harmful gases.
Step 2: Signal Processing
The microcontroller receives signals from sensors and confirms fire detection.
Step 3: Automatic Actions
Immediately:
⚡ Cuts local electricity in that forest zone.
🔔 Activates warning buzzer in nearby villages.
📩 Sends SMS alert to forest department and fire station.
📱 Updates live data on IoT dashboard.
💧 Starts underground water pump.
🚿 Sprinklers spray water only in affected area.
Step 4: Monitoring
Officials can monitor the situation remotely through mobile app.
6️⃣ Unique Features
⭐ Zonal Fire Detection (Only affected area activated)
⭐ Automatic Power Cut System
⭐ Real-Time SMS Alert
⭐ IoT Monitoring
⭐ Solar Backup
⭐ Water Saving Smart Sprinkler
⭐ Village Warning System
7️⃣ Advantages
Early fire detection
Saves trees and wildlife
Reduces human risk
Automatic emergency response
Cost-effective for large forests
Works 24/7
8️⃣ Future Improvements
Add AI-based image detection using camera.
Add drone monitoring system.
Connect with satellite data.
Use temperature and humidity sensors.
Government forest network integration.
9️⃣ Social Impact
FLAME GUARD can:
Protect environment
Reduce air pollution
Save villages near forests
Protect wildlife
Support government forest departments
This project supports environmental protection goals and sustainable development.
🔟 Conclusion
FLAME GUARD is an innovative, smart, and life-saving forest fire prevention system. By combining IoT, automation, and real-time alerts, it provides early detection and quick response to forest fires.
This system can reduce forest damage, protect wildlife, and save human lives.
💥 Powerful Ending Line for Judges
“FLAME GUARD – Protecting Forests Before Fire Destroys Them.”


# 🔥🌳 FLAMEGUARD - Smart Forest Fire Detection System

## 📌 Project Description
FLAMEGUARD is an Arduino-based smart system designed to detect fire and smoke in forest areas at an early stage. It detects fire quickly and activates a buzzer and water pump automatically to stop fire spread.
⭐ Real-Time SMS Alert

⭐ IoT Monitoring

⭐ Solar Backup

⭐ Water Saving Smart Sprinkler💧

⭐ Village Warning System

7️⃣ Advantage

🔥Early fire detection

Saves trees and wildlife🐅

Reduces human risk👨‍💼

💹Automatic emergency response

Cost-effective for large forests

Works 24/7

8️⃣ Future improvements

Add AI-based image detection using camera.

*Add drone monitoring system.

*Connect with satellite data.

*Use temperature and humidity sensors.

*Government forest network integration.

9️⃣ Social impact

*FLAME GUARD can:

*Protect environment🌳

*Reduce air pollution🍃🎐

*Save villages near forests

*Protect wildlife🐅🌳

*Support government forest departments

This project supports environmental 🎐protection goals and sustainable development.

🔟 Conclusion

*FLAME GUARD 🔥is an innovative, smart, and life-saving forest fire prevention system. By combining IoT, automation, and real-time alerts, it provides early detection and quick response to forest fires.

This system can reduce forest damage, protect wildlife, and save human lives.

💥 Powerful Ending Line for Judges

“FLAME GUARD 🔥– Protecting Forests Before Fire Destroys Them.”

## 🚀 Features
- 🔥 Fire detection
- 💨 Smoke detection
- 🚨 Alarm system
- 💧 Automatic water spray
- 🔄 Servo movement

## 🧰 Components
- Arduino Uno
- Flame Sensor
- MQ-2 Sensor
- Servo Motor
- Water Pump
- Buzzer
- sprinkler 
- underground tank
- solar panel

🔌 Complete Wire Connections (Simple)
🔥 1. Flame Sensor
VCC → 5V (Arduino)
GND → GND
DO → Pin 2
💨 2. MQ-2 Smoke Sensor
VCC → 5V
GND → GND
AO → A0
🔊 3. Buzzer
+ (Positive) → Pin 8
– (Negative) → GND
🔄 4. Servo Motor
Red → 5V
Brown → GND
Orange → Pin 9
💧 5. Water Pump (VERY IMPORTANT ⚠️)
👉 Do NOT connect pump directly to Arduino
Use Relay Module or Transistor
✔️ Using Relay (Best)
Relay VCC → 5V
Relay GND → GND
Relay IN → Pin 7
Pump Connection:
Battery + → Relay COM
Relay NO → Pump +
Pump – → Battery –
⚡ Power Notes
Arduino → USB power
Pump → Separate battery (6V–12V)
🔥 Simple Working Flow
Fire detected 🔥
→ Buzzer ON 🚨
→ Pump ON 💧
→ Servo moves 🔄

## 💻 Code
(#include <Servo.h>

int flamePin = 2;      // Flame sensor digital pin
int smokePin = A0;    // MQ-2 analog pin
int buzzer = 8;       // Buzzer pin
int pump = 7;         // Water pump (via relay)
int smokeThreshold = 300;  // Adjust based on testing

Servo myServo;

void setup() {
  pinMode(flamePin, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(pump, OUTPUT);

  myServo.attach(9);   // Servo pin

  Serial.begin(9600);
}

void loop() {
  int flame = digitalRead(flamePin);   // LOW = fire detected
  int smoke = analogRead(smokePin);

  Serial.print("Smoke Level: ");
  Serial.println(smoke);

  // Check for fire or smoke
  if (flame == LOW || smoke > smokeThreshold) {
    
    digitalWrite(buzzer, HIGH);  // Turn ON buzzer
    digitalWrite(pump, HIGH);    // Turn ON pump

    // Move servo (water spray)
    myServo.write(0);
    delay(500);
    myServo.write(90);
    delay(500);
    myServo.write(180);
    delay(500);

  } else {
    digitalWrite(buzzer, LOW);   // Turn OFF buzzer
    digitalWrite(pump, LOW);     // Turn OFF pump
  }

  delay(500);
}
## 🎥 Demo Video
(https://youtube.com/shorts/wQEadi6Kaf0?si=WeqVK4LdKd78utie)

## 👨‍💻 Made By
Abhishek