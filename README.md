# 🔥🌳 FLAMEGUARD - Smart Forest Fire Detection System

## 📌 Project Description
FLAMEGUARD is an Arduino-based smart system designed to detect fire and smoke in forest areas at an early stage. It detects fire quickly and activates a buzzer and water pump automatically to stop fire spread.

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
(Add your YouTube link here)

## 👨‍💻 Made By
Abhishek