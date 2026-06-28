# LED Control with Arduino Uno

A simple Arduino project that demonstrates how to control multiple LEDs using an Arduino Uno. The LEDs turn on and off sequentially, creating a basic light pattern that is ideal for beginners learning digital outputs and LED control.

> **Note:** The circuit diagram includes a pushbutton, but the current code only performs sequential LED blinking and does not use the pushbutton functionality. You can extend the project by adding button-controlled behavior later. :contentReference[oaicite:0]{index=0}

![Project Preview](LED%20blink%20by%20Pushbutton.png)

---

## 📌 Features

- Controls **3 LEDs** using digital output pins.
- Sequential LED blinking with 1-second intervals.
- Beginner-friendly Arduino project.
- Easy to modify for pushbutton interaction.
- Demonstrates basic Arduino programming concepts.

---

## 🛠️ Components Required

| Component | Quantity |
|-----------|----------|
| Arduino Uno | 1 |
| LEDs | 3 |
| 220Ω Resistors | 3 |
| Pushbutton | 1 |
| Breadboard | 1 |
| Jumper Wires | Several |
| USB Cable | 1 |

---

## 🔌 Circuit Connections

| Arduino Pin | Component |
|-------------|-----------|
| D10 | LED 1 |
| D11 | LED 2 |
| D12 | LED 3 |
| GND | LED Cathodes (through 220Ω resistors) |
| Pushbutton | Connected as shown in the circuit diagram |

---

## 📂 Project Structure

```text
LED-Control-With-Pushbutton/
│── LED blink By Pushbutton.cpp
│── LED blink by Pushbutton.png
└── README.md
```

---

## 🚀 How It Works

1. The Arduino turns on **LED 1** for one second.
2. LED 1 turns off.
3. **LED 2** turns on for one second.
4. LED 2 turns off.
5. **LED 3** turns on for one second.
6. LED 3 turns off.
7. The sequence repeats continuously.

Although a pushbutton is included in the wiring diagram, it is **not currently used in the code**. The LEDs blink automatically in sequence. :contentReference[oaicite:1]{index=1}

---

## 💻 Code Overview

The LEDs are assigned to digital pins:

```cpp
const int LED_1 = 10;
const int LED_2 = 11;
const int LED_3 = 12;
```

Each LED is switched on and off using:

```cpp
digitalWrite(LED_1, HIGH);
delay(1000);
digitalWrite(LED_1, LOW);
```

The same process is repeated for all three LEDs. :contentReference[oaicite:2]{index=2}

---

## ▶️ Uploading the Sketch

1. Open the project in the **Arduino IDE**.
2. Connect your Arduino Uno via USB.
3. Select:
   - **Board:** Arduino Uno
   - **Port:** Your Arduino COM Port
4. Upload the sketch.
5. Observe the LEDs blinking one after another.

---

## 📖 Learning Objectives

This project introduces:

- Digital output pins
- Using `digitalWrite()`
- Arduino `setup()` and `loop()`
- Timing with `delay()`
- LED sequencing
- Basic breadboard wiring

---

## 🔮 Future Improvements

- Implement actual pushbutton functionality.
- Toggle LEDs using the button.
- Change blink patterns with button presses.
- Add PWM fading effects.
- Use interrupts for responsive button input.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**ADITYA**

GitHub: https://github.com/aditya
