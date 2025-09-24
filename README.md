# Aztec Platforms
## AP-ESP32S3DC1-PB-1V4
In this Documentation we will explore the Aztec Platforms AP-ESP32S3DC1-PB-1V4. This board is designed to be a versitile project board that can be used in many ways. The main reason I design these boards is to reduce the amount of wiring for simple tasks like voltage reduction, common pinout placement, PSU jankery, etc.

Designed to get your projects off the ground faster, and, suitable for use in long term and permanent projects.

# Design Overview

### Board Size and hole spacing

<p align="center">
<img src="https://github.com/user-attachments/assets/3cc55f01-26e6-490c-bf75-1ed6568e0f5a" alt="Board and Hole Size" width="600">
</p>

---

### Power Rails

This board provides three usable voltage rails — Vin (whatever voltage you supply the board with), 5 V, and 3.3 V — making it versatile for a wide range of projects and connected devices.

Powering the board is done by connecting input wires to the obard screw terminal header on the left side of the board. I would highly reccommend you use 12V @ 5A.

Once 12 V is available on the board, it is stepped down in two stages:
- 12 V → 5 V
- 12 V → 3.3 V

The ESP32-S3 runs on 3.3 V, which is also the voltage used by most sensors and peripherals. The 5 V rail is handy for certain modules, and the raw Vin input remains available as well.

This design keeps the board simple, flexible, and safe while giving you multiple voltage rails to power different devices.

---

### Level Translator (Level Shifter) and Pin Voltages

Another key feature of this board, made possible by the 3.3 V and 5 V rails, is the level shifter. This component translates signals between 3.3 V (from the ESP32-S3) and 5 V, enabling you to control devices that require 5 V inputs. For example, the PWM input on a computer fan expects a 5 V signal, so you couldn’t drive it directly from the ESP32 alone.

The level shifter also works in reverse: it safely steps down 5 V input signals to 3.3 V, protecting the ESP32-S3 pins. This is particularly useful when working with sensors that output only 5 V, as connecting them directly could damage the microcontroller.

For each level-shifted signal, you’ll notice duplicate pins: one for the 3.3 V side and one for the 5 V side. ⚠️ Important: these pairs are electrically connected. You can use either the 3.3 V or the 5 V version of a pin (e.g., D0), but not both at the same time.

<p align="center">
<img src="https://github.com/user-attachments/assets/8c019823-ccd9-4054-839f-3a8880111cb1" width="600">
</p>


---

### N-Channel Mosfet

<p align="center">
<img src="https://github.com/user-attachments/assets/066d6ef1-1488-411a-90ee-e34a9e93c5c9" alt="Board and Hole Size" width="600">
</p>


---

## License
This repository is licensed under a custom Source-Available License.  
- ✅ Personal, hobbyist, and educational use of the code is allowed.  
- ❌ Commercial use, redistribution, and modification of images/docs are prohibited.  
- ℹ️ See [LICENSE](./LICENSE) for details. 
