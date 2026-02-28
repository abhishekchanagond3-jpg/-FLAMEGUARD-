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