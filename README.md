# SECURITY-SYSTEM

COMPANY NAME:CODTECH IT SOLUTION

NAME:S.GOKUL

INTERN ID:CT04DZ1667

DOMAIN:INTERNET OF THINGS

DURATION:4 WEEKS

MENTOR:NEELA SANTHOSH

# 🛡 Task 3: IoT Security System – IoT Internship (CODTECH IT Solutions)

## 📘 Overview

This project is the third task of my IoT internship at *CODTECH IT Solutions. It focuses on building a basic **IoT-based Security System* using Arduino UNO, a PIR motion sensor, and an alert indicator (LED). The system detects motion and provides a visual alert, simulating a home or office security alarm.

## ⚙ Functionality

- Uses a *PIR sensor* to detect human motion.
- When motion is detected:
  - A *LED turns ON* to indicate an alert.
  - A *message is printed in the Serial Monitor*.
- When no motion is detected:
  - LED remains OFF.
  
This simulates a real-world intrusion detection setup.

## 🛠 Tools & Components

- Arduino UNO (Wokwi)
- PIR Motion Sensor
- LED (for alert)
- 220Ω Resistor
- Jumper Wires
- Serial Monitor (for alert messages)

## 🔌 Circuit Setup

| Component     | Arduino Pin | Description                  |
|---------------|-------------|------------------------------|
| PIR Sensor OUT| Pin 2       | Motion signal input          |
| PIR VCC       | 5V          | Power supply                 |
| PIR GND       | GND         | Ground connection            |
| LED + (Anode) | Pin 13      | Output to LED via resistor   |
| LED - (Cathode)| GND        | Connected directly to ground |

## 💻 Code Summary

```cpp
#define PIR_PIN 2
#define ALERT_LED 13

void setup() {
  pinMode(PIR_PIN, INPUT);
  pinMode(ALERT_LED, OUTPUT);
  Serial.begin(9600);
  Serial.println("System Ready. Waiting for motion...");
}

void loop() {
  int motionState = digitalRead(PIR_PIN);
  
  if (motionState == HIGH) {
    digitalWrite(ALERT_LED, HIGH);
    Serial.println("⚠ Motion Detected! Security Alert!");
    delay(1000);  // debounce
  } else {
    digitalWrite(ALERT_LED, LOW);
  }
}


#OUTPUT

<img width="960" height="540" alt="Image" src="https://github.com/user-attachments/assets/021b7ebe-a127-42e0-b81f-98b40e75cdb5" />
<img width="960" height="540" alt="Image" src="https://github.com/user-attachments/assets/31bf70b4-416a-46f8-b57f-541f532618c7" />
