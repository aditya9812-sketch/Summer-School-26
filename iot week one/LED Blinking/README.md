# LED Sequential Fade with Arduino Uno

A simple Arduino project that demonstrates how to control multiple LEDs using **PWM (Pulse Width Modulation)** to create a smooth fade-in and fade-out effect. Each LED lights up one at a time, gradually increasing and decreasing in brightness before moving to the next LED.

![Project Preview](LED%20Blinking.png)

📌 Features

* Controls **3 LEDs** connected to PWM pins.
* Smooth **fade-in** and **fade-out** animation.
* Sequential LED operation.
* Beginner-friendly Arduino project.
* Demonstrates the use of:

  * Arrays
  * `for` loops
  * `analogWrite()`
  * PWM outputs

 🛠️ Components Required

| Component        | Quantity |
| ---------------- | -------- |
| Arduino Uno      | 1        |
| LEDs (Any Color) | 3        |
| 220Ω Resistors   | 3        |
| Breadboard       | 1        |
| Jumper Wires     | Several  |
| USB Cable        | 1        |

 🔌 Circuit Connections

| Arduino Pin | Component                               |
| ----------- | --------------------------------------- |
| D9          | LED 1 (+)                               |
| D10         | LED 2 (+)                               |
| D11         | LED 3 (+)                               |
| GND         | All LED cathodes through 220Ω resistors |

Each LED should be connected in series with a **220Ω resistor** to protect it from excessive current.

---

## 📂 Project Structure

```text
LED-Sequential-Fade/
│── LED Blinking.cpp
│── LED Blinking.png
└── README.md
```

---

## 🚀 How It Works

1. Three PWM pins (9, 10, and 11) are stored in an array.
2. The program loops through each LED.
3. Each LED:

   * Gradually fades from **0 → 255 brightness**
   * Then fades from **255 → 0 brightness**
4. After one LED finishes, the next LED starts.

This process repeats forever.

---

## 💻 Code Overview

The sketch uses:

```cpp
int LED[] = {9, 10, 11};
```

to store all LED pins, making the program scalable and easier to maintain.

Brightness is controlled using:

```cpp
analogWrite(pin, brightness);
```

where `brightness` ranges from **0** (off) to **255** (fully on). 

---

## ▶️ Uploading the Sketch

1. Open the project in the **Arduino IDE**.
2. Connect your Arduino Uno via USB.
3. Select:

   * **Board:** Arduino Uno
   * **Port:** Your Arduino COM Port
4. Upload the sketch.
5. Watch each LED smoothly fade in and out.

---

## 📖 Learning Objectives

This project helps you understand:

* PWM outputs on Arduino
* Arrays in C++
* `for` loops
* Functions (`setup()` and `loop()`)
* Controlling LED brightness
* Basic electronics and breadboard wiring

---

## 🔮 Future Improvements

* Add push-button controls.
* Synchronize multiple LEDs.
* Create breathing or wave effects.
* Use RGB LEDs for color fading.
* Add potentiometer speed control.

---

## 📜 License

This project is open source and available under the **MIT License**.

---

## 👨‍💻 Author

**ADITYA**

GitHub: `https://github.com/aditya
