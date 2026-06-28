# Arduino Serial-Controlled Servo Gate System

A simple Arduino project that demonstrates **serial communication between two Arduino Uno boards** to control a servo motor. One Arduino acts as the **controller**, reading a push button and sending commands (`OPEN` or `CLOSE`) over the serial port. The second Arduino receives these commands and rotates a servo motor to simulate an automated gate.

![Project Preview](servo%20motor.png)

---

## 📌 Features

- Uses **two Arduino Uno boards**.
- Controls a **servo motor** using serial communication.
- Push button opens and closes the gate.
- Utilizes the built-in `Servo` library.
- Beginner-friendly project demonstrating Arduino-to-Arduino communication.

---

## 🛠️ Components Required

| Component | Quantity |
|-----------|----------|
| Arduino Uno | 2 |
| Servo Motor (SG90 or similar) | 1 |
| Push Button | 1 |
| 10kΩ Resistor (optional if not using INPUT_PULLUP) | 1 |
| Jumper Wires | Several |
| USB Cable | 2 |

---

## 🔌 Circuit Connections

### Arduino 1 (Controller)

| Arduino Pin | Component |
|-------------|-----------|
| D2 | Push Button |
| GND | Push Button |
| TX (D1) | RX (D0) of Arduino 2 |
| GND | Common Ground |

---

### Arduino 2 (Servo Controller)

| Arduino Pin | Component |
|-------------|-----------|
| D9 | Servo Signal |
| 5V | Servo VCC |
| GND | Servo GND |
| RX (D0) | TX (D1) of Arduino 1 |
| GND | Common Ground |

> **Important:** Both Arduino boards **must share a common ground** for serial communication to work correctly.

---

## 📂 Project Structure

```text
Arduino-Servo-Gate-System/
│── Controller.ino
│── Servo_Controller.ino
│── servo motor.png
└── README.md
```

---

## 🚀 How It Works

### Arduino 1 (Controller)

1. Configures the push button using `INPUT_PULLUP`.
2. Detects button state changes.
3. Sends:
   - `OPEN` when the button is pressed.
   - `CLOSE` when the button is released.

---

### Arduino 2 (Servo Controller)

1. Waits for serial commands.
2. If it receives:

```
OPEN
```

the servo rotates to **90°**.

3. If it receives:

```
CLOSE
```

the servo returns to **0°**.

4. A confirmation message is printed to the Serial Monitor.

---

## 💻 Code Overview

### Controller Arduino

- Reads the push button.
- Detects state changes.
- Sends serial commands.

```cpp
if (currentState == LOW) {
    Serial.println("OPEN");
} else {
    Serial.println("CLOSE");
}
```

---

### Servo Arduino

- Reads incoming serial data.

```cpp
command = Serial.readStringUntil('\n');
```

Moves the servo:

```cpp
gateServo.write(90);   // Open Gate
gateServo.write(0);    // Close Gate
```

---

## ▶️ Uploading the Sketch

### Arduino 1

1. Open **Controller.ino**.
2. Select **Arduino Uno**.
3. Upload the sketch.

### Arduino 2

1. Open **Servo_Controller.ino**.
2. Select **Arduino Uno**.
3. Upload the sketch.

After both sketches are uploaded:

- Connect the TX/RX pins as shown in the circuit.
- Press the push button.
- The servo will rotate between **0°** and **90°**.

---

## 📖 Learning Objectives

This project demonstrates:

- Arduino-to-Arduino serial communication
- Push button interfacing
- Servo motor control
- Using the Servo library
- Reading serial commands
- Event-driven programming
- Embedded systems communication

---

## 🔮 Future Improvements

- Add an LCD to display gate status.
- Integrate an RFID module for access control.
- Control the gate using Bluetooth (HC-05).
- Add Wi-Fi control using ESP8266/ESP32.
- Include an ultrasonic sensor for automatic gate operation.
- Add LEDs and a buzzer for status indication.

---

## ⚠️ Notes

- Disconnect the **TX/RX wires** while uploading code to avoid upload errors.
- Ensure both Arduino boards share a **common GND**.
- If using a larger servo, power it from an **external 5V supply** instead of the Arduino.
- The button uses `INPUT_PULLUP`, so:
  - **Pressed = LOW**
  - **Released = HIGH**

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**ADITYA**

GitHub: https://github.com/aditya

---

⭐ If you found this project helpful, consider giving it a **Star** on GitHub!
