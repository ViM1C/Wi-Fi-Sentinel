# Wi-Fi-Sentinel
Portable Wi-Fi scanning and visualization tool for the M5Stack Cardputer (ESP32-S3). Runs fully standalone with real-time signal analysis and a color-coded dashboard.

# Wi-Fi Sentinel – Portable Wireless Network Scanner  

![Made with MicroPython](https://img.shields.io/badge/Made%20with-MicroPython-blue)  
![Platform: ESP32-S3](https://img.shields.io/badge/Platform-ESP32--S3-green)  
![Status: Active](https://img.shields.io/badge/Status-Active-brightgreen)  

Wi-Fi Sentinel turns the $30 **M5Stack Cardputer** into a **self-contained Wi-Fi scanning and visualization tool**.  

Power it on, and it automatically scans nearby Wi-Fi networks, showing **real-time signal strength** with **color-coded indicators** on its built-in display — no PC or terminal required.  

---

## ✨ Features  

- **Autonomous Scanning:** Boots and runs standalone — no external control needed.  
- **Color-Coded Dashboard:** Green = strong, Yellow = medium, Red = weak signals.  
- **Continuous Monitoring:** Auto-refresh cycles keep results up to date in real time.  
- **Portable Form Factor:** Runs on a compact ESP32-S3 microcontroller with limited resources.  

---

## 🛠 Tech Stack  

| Component     | Details                         |
|---------------|---------------------------------|
| **Hardware**   | M5Stack Cardputer (ESP32-S3)     |
| **Language**   | MicroPython + UIFlow2 APIs       |
| **Libraries**  | M5, Display, network             |

---

## 🚀 Why It Matters  

Wi-Fi Sentinel isn’t just a blinking demo — it’s a showcase of:  

- **IoT & Embedded Programming** on constrained hardware  
- **Real-Time Wireless Reconnaissance** automation  
- **Data Visualization** in resource-limited environments  

Future enhancements could include **data logging, signal mapping, or security alerts** — turning it into a full wireless analysis toolkit.  

---

## 📸 Demo  
  
![Wi-Fi Sentinel Demo](https://raw.githubusercontent.com/ViM1C/Wi-Fi_Sentinel/main/1000003953.jpg)



  

---

## 📦 Getting Started  

1. **Flash Firmware:** Install MicroPython or UIFlow2 on the M5Stack Cardputer.  
2. **Upload Script:** Copy the Wi-Fi Sentinel code using Thonny or ampy.  
3. **Run Standalone:** Power on the device — scanning starts automatically.  

---

## 🖥 Quickstart Example  

```python
import network, time
from M5 import M5Screen

screen = M5Screen()
screen.clean_screen()
wifi = network.WLAN(network.STA_IF)
wifi.active(True)

while True:
    nets = wifi.scan()
    screen.print("Wi-Fi Networks:")
    for ssid, bssid, channel, rssi, auth, hidden in nets:
        color = "Green" if rssi > -60 else "Yellow" if rssi > -75 else "Red"
        screen.print(f"{ssid} | {rssi} dBm | {color}")
    time.sleep(5)
    screen.clean_screen()
```

---

## 📜 License  

This project is open-source under the **MIT License**.  


