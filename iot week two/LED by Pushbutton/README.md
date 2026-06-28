# LED Control Using a Push Button | Arduino Uno

A simple Arduino project that demonstrates how to control an LED using a **push button**. The project introduces digital input and output concepts by reading the state of a push button and controlling an LED based on user interaction.

> **Note:** The provided code is a basic implementation and contains a few syntax and logic issues that should be corrected before uploading to the Arduino. This project is ideal for beginners learning about push buttons, digital inputs, and LED control.

![Project Preview](LED%20by%20Pushbutton.png)

---

## 📌 Features

- Control an LED using a push button.
- Demonstrates digital input and output.
- Uses `digitalRead()` and `digitalWrite()`.
- Beginner-friendly Arduino project.
- Easy to expand with additional LEDs or button functions.

---

## 🛠️ Components Required

| Component | Quantity |
|-----------|----------|
| Arduino Uno | 1 |
| LED | 1 |
| 220Ω Resistor (LED) | 1 |
| 10kΩ Resistor (Pull-down) | 1 |
| Push Button | 1 |
| Jumper Wires | Several |
| USB Cable | 1 |

---

## 🔌 Circuit Connections

| Arduino Pin | Component |
|-------------|-----------|
| D2 | Push Button |
| D3 | LED Anode (+) |
| GND | LED Cathode (through 220Ω resistor) |
| GND | Pull-down resistor |

The push button is connected to **Digital Pin 2**, while the LED is connected to **Digital Pin 3** through a current-limiting resistor.

---

## 📂 Project Structure

```text
LED-Control-With-PushButton/
│── LED by Pushbutton.ino
│── LED by Pushbutton.png
└── README.md
```

---

## 🚀 How It Works

1. The Arduino continuously reads the state of the push button.
2. When the button is pressed, the LED turns **ON**.
3. When the button is released, the LED turns **OFF**.
4. The button state is also sent to the **Serial Monitor** for debugging.

---

## 💻 Code Overview

The program:

- Configures **Pin 2** as the button input.
- Configures **Pin 3** as the LED output.
- Reads the button state using:

```cpp
buttonState = digitalRead(2);
```

- Turns the LED on or off using:

```cpp
digitalWrite(LED, HIGH);
digitalWrite(LED, LOW);
```

- Prints the button state to the Serial Monitor.

---

## ▶️ Uploading the Sketch

1. Open the project in the **Arduino IDE**.
2. Connect your Arduino Uno via USB.
3. Select:
   - **Board:** Arduino Uno
   - **Port:** Your Arduino COM Port
4. Upload the sketch.
5. Open the **Serial Monitor** (9600 baud).
6. Press the button to control the LED.

---

## 📖 Learning Objectives

This project introduces:

- Digital Inputs
- Digital Outputs
- Push Button Interfacing
- Reading Switch States
- Serial Communication
- Basic Arduino Programming

---

## ⚠️ Code Improvements

The uploaded code contains a few issues that should be corrected:

- Missing semicolon after:

```cpp
delay(10);
```

- The button state is read only once before entering the `while` loop, causing the program to become stuck while the button remains pressed.

- Using a `while` loop is unnecessary. An `if` statement is more appropriate:

```cpp
buttonState = digitalRead(2);

if (buttonState == HIGH) {
    digitalWrite(LED, HIGH);
} else {
    digitalWrite(LED, LOW);
}
```

- If you're using a pull-down resistor, `HIGH` usually indicates the button is pressed. If you're using the Arduino's internal pull-up resistor (`INPUT_PULLUP`), the logic is reversed.

---

## 🔮 Future Improvements

- Toggle the LED with each button press.
- Add multiple LEDs.
- Control LED brightness using PWM.
- Implement button debouncing.
- Add long-press and double-click functionality.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**ADITYA**

GitHub: https://github.com/aditya
