# 🤖 Dasai Mochi Custom Firmware for ESP32-C6

An intelligent Dasai Mochi animation and notification device firmware built on ESP32-C6 Super Mini and SSD1306 OLED display, integrated with the **Chronos App** (BLE).

> 💡 **Acknowledgement / Credits:**
> This project is a custom Dasai Mochi clone firmware for ESP32-C6, directly inspired by and based on the work of [huykhoong/esp32_dasai_mochi_clone_and_how_to](https://github.com/huykhoong/esp32_dasai_mochi_clone_and_how_to).

---

## 📌 Features

* **Mochi Face Animations:** Smooth face animations on SSD1306 (128x64 OLED) with automatic transition to "resting face" mode between cycles.
* **BLE Notification System:** Bluetooth Low Energy integration via **Chronos App** to display smartphone notifications (SMS, calls, app alerts) on a sleek OLED card GUI for 20 seconds.
* **Real-time Navigation *(Experimental / Untested)*:** Turn-by-turn guidance integration for Google Maps or OSMAnd, displaying directional icons, distance, duration, and remaining travel time. *(Note: Google Maps navigation support is currently under development and has not been fully tested yet).*
* **Touch & Power Management *(In Development / Untested)*:** TTP223 (or similar touch sensor on Pin 18) planned controls for power management and waking up:
  * **Double Click:** Wake up device / Turn on screen.
  * **Long Press (2 sec):** Turn off display & BLE to enter low-power Light Sleep.

---

## 🛠 Hardware & Wiring Diagram

### Required Components
* **MCU:** ESP32-C6 Super Mini
* **Display:** 0.96" SSD1306 I2C OLED Display (128x64)
* **Sensor:** TTP223 Touch Sensor Module (or equivalent digital touch sensor)

### Pinout Configuration

| ESP32-C6 Pin | Component Pin | Description |
| :--- | :--- | :--- |
| **GPIO 19** | SDA | OLED Display I2C Data |
| **GPIO 20** | SCL | OLED Display I2C Clock |
| **GPIO 18** | SIG | Touch Sensor Signal Input |
| **3V3** | VCC | OLED & Sensor Power |
| **GND** | GND | Common Ground |

> ⚠️ **Note:** I2C silk screens may vary between ESP32-C6 Super Mini clone boards. Always double-check your board pinout before wiring.

---

## 📦 Library Dependencies

Make sure the following libraries are installed via Arduino IDE Library Manager before compiling:

1. **Adafruit GFX Library**
2. **Adafruit SSD1306**
3. **ChronosESP32** (`fbiego/chronos-esp32`)
4. **NimBLE-Arduino** *(ChronosESP32 dependency - **v2.5.1** or higher required)*
5. **ESP32Time** *(ChronosESP32 dependency)*

---

## ⚙ Setup & Flashing

1. **Arduino IDE Configuration:**
   * **Board Manager URL:** `https://espressif.github.io/arduino-esp32/package_esp32_index.json`
   * Update the **esp32** core to `3.x.x` or newer.
   * Select Board: **ESP32C6 Dev Module**

2. **Upload:**
   * Clone the repo and open the `.ino` sketch in Arduino IDE.
   * Ensure all dependencies are installed.
   * Connect board over USB, select the correct COM port, and upload.

3. **Mobile App Pairing:**
   * Download the **Chronos** app on Android or iOS.
   * Go to **Watches > Pair New Devices**.
   * Pair with **"Dasai Mochi"**.

---

## 📄 License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**. See the `LICENSE` file for details.
