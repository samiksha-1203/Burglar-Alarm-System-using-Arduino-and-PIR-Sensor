# 🔐 Burglar Alarm System using Arduino and PIR Sensor

## 📌 Overview
This project is a simple and cost-effective security system that detects motion using a PIR (Passive Infrared) sensor. When motion is detected, an alarm (buzzer) is triggered to alert the user.

---

## ⚙️ Components Used
- Arduino Uno  
- PIR Sensor  
- Buzzer  
- Jumper Wires  
- Power Supply (5V/USB)  

---

## 🔌 Circuit Diagram (Connections)

| Component | Arduino Pin |
|----------|------------|
| PIR VCC  | 5V         |
| PIR GND  | GND        |
| PIR OUT  | Pin 8      |
| Buzzer + | Pin 11     |
| Buzzer - | GND        |

---

## 🚀 Working Principle
- PIR sensor detects motion by sensing infrared radiation from human body  
- When motion is detected → output becomes HIGH  
- Arduino reads the signal and activates the buzzer  
- When no motion → buzzer turns OFF  

---

## 💻 Arduino Code

```cpp
int buzzerPin = 11;
int inputPin = 8;
int pirState = LOW;
int val = 0;

void setup() {
  pinMode(buzzerPin, OUTPUT);
  pinMode(inputPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  val = digitalRead(inputPin);

  if (val == HIGH) {
    digitalWrite(buzzerPin, HIGH);

    if (pirState == LOW) {
      Serial.println("Motion detected!");
      pirState = HIGH;
    }
  } 
  else {
    digitalWrite(buzzerPin, LOW);

    if (pirState == HIGH) {
      Serial.println("Motion ended!");
      pirState = LOW;
    }
  }
}
```

---

## 🔍 Applications
- Home security systems  
- Office surveillance  
- Restricted area monitoring  
- Smart automation systems  

---

## 💡 Features
- Low cost and easy to build  
- Real-time motion detection  
- Simple circuit design  

---

## 👩‍💻 Authors
Samiksha Chavan & Team
