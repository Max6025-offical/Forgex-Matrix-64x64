# {{PROJECT_NAME}} 🚀  
> Advanced RGB Matrix Display System for real-time printer visualization on a 64×64 LED panel

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python)
![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi-red?logo=raspberrypi)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Build-Stable-success)

---

## 🧠 Overview  
{{PROJECT_NAME}} is a **dynamic RGB matrix display system** built for **64×64 LED panels** (HUB75 / RGBMatrix HAT).  
It connects to a **Moonraker printer API** to visualize real-time printing states such as:

- 🟢 **Standby / Ready**  
- 🔵 **Printing (with live progress bar)**  
- 🟠 **Paused / Waiting**  
- 🔴 **Error / Aborted**  
- ⚪ **Complete / Finished**  

All animations are optimized for smooth transitions, clean visuals, and stable operation on Raspberry Pi.

---

## ⚙️ Features  

| Category | Description |
|-----------|--------------|
| 🎞️ **Animations** | Smooth transitions, easing effects, boot sequences |
| 🔌 **API Integration** | Live printer data from Moonraker (`/printer/objects/query`) |
| ⚡ **Performance** | Hardware-accelerated rendering with `rgbmatrix` |
| 🧩 **Configuration** | Full control via `config.ini` |
| 🧠 **Simulation Mode** | Test animations without a printer connection |
| 🧱 **Lock Mechanism** | Prevents multiple instances (singleton lock) |
| 📜 **Logging** | Debug logs written to file (`/var/log/matrix64/api.log`) |

---

## 🧩 Project Structure  

