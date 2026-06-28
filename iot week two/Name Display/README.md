# Arduino LCD I2C Name Display

A beginner-friendly Arduino project that demonstrates how to interface a **16×2 I2C LCD Display** with an **Arduino Uno**. The project initializes the LCD, enables the backlight, and displays a custom message ("ADITYA") on the first line of the screen.

![Project Preview](Name%20DISPLAY.png)

---

## 📌 Features

- Displays text on a **16×2 I2C LCD**.
- Uses the **LiquidCrystal_I2C** library.
- Simple and beginner-friendly Arduino project.
- Demonstrates I2C communication.
- Easily customizable to display any text.

---

## 🛠️ Components Required

| Component | Quantity |
|-----------|----------|
| Arduino Uno | 1 |
| 16×2 I2C LCD Display | 1 |
| Jumper Wires | 4 |
| USB Cable | 1 |

---

## 🔌 Circuit Connections

| LCD Pin | Arduino Uno |
|----------|-------------|
| GND | GND |
| VCC | 5V |
| SDA | A4 |
| SCL | A5 |

> **Note:** On the Arduino Uno, the SDA and SCL pins are also available on the dedicated SDA and SCL header pins.

---

## 📂 Project Structure

```text
Arduino-LCD-I2C-Name-Display/
│── Name DISPLAY.ino
│── Name DISPLAY.png
└── README.md
```

---

## 🚀 How It Works

1. The Arduino initializes the I2C LCD.
2. The LCD backlight is turned on.
3. The cursor is positioned at the first column of the first row.
4. The text **"ADITYA"** is displayed on the LCD.
5. Since the `loop()` function is empty, the message remains displayed continuously.

---

## 💻 Code Overview

The project uses the following libraries:

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
```

An LCD object is created with the I2C address:

```cpp
LiquidCrystal_I2C lcd(0x20, 16, 2);
```

The display is initialized with:

```cpp
lcd.init();
lcd.backlight();
lcd.setCursor(0, 0);
lcd.print("ADITYA");
```

---

## ▶️ Uploading the Sketch

1. Install the **LiquidCrystal_I2C** library using the Arduino Library Manager.
2. Open the project in the **Arduino IDE**.
3. Connect your Arduino Uno via USB.
4. Select:
   - **Board:** Arduino Uno
   - **Port:** Your Arduino COM Port
5. Upload the sketch.
6. The LCD will display:

```
ADITYA
```

---

## 📖 Learning Objectives

This project introduces:

- I2C Communication
- LCD Display Interfacing
- Using External Arduino Libraries
- Displaying Text on an LCD
- Arduino Setup and Initialization
- Basic Embedded Systems Programming

---

## ⚠️ Note About the I2C Address

Your code uses the I2C address:

```cpp
LiquidCrystal_I2C lcd(0x20, 16, 2);
```

Many 16×2 I2C LCD modules use **0x27** or **0x3F** instead. If your display does not work, use an **I2C Scanner** sketch to determine the correct address and update your code accordingly.

---

## 🔮 Future Improvements

- Display scrolling text.
- Show sensor readings (temperature, humidity, etc.).
- Create a digital clock.
- Display menu options using push buttons.
- Add custom LCD characters and animations.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**ADITYA**

GitHub: https://github.com/aditya

---

⭐ If you found this project helpful, consider giving it a **Star** on GitHub!
