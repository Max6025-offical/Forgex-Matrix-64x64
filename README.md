# Forgex-Matrix-64x64 🚀  
> Advanced RGB Matrix Display System for real-time printer visualization on a 64×64 LED panel

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python)
![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi-red?logo=raspberrypi)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Build-Stable-success)

---

## 🧠 Overview  
**Forgex-Matrix-64x64** is a dynamic **RGB matrix display system** built for **64×64 LED panels** (HUB75 / RGBMatrix HAT).  
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
| 🧩 **Configuration** | Full control via `config.ini` (auto-created on first run) |
| 🧠 **Simulation Mode** | Test animations without a printer connection |
| 🧱 **Lock Mechanism** | Prevents multiple instances (singleton lock) |
| 📜 **Logging** | Debug logs written to file (`/var/log/matrix64/api.log`) |

---

## 🧩 Project Structure  

forgex-matrix-64x64/  
├── matrix.py              # Main application (core logic)  
├── config.ini             # Configuration file (auto-generated if missing)  
├── fonts/                 # BDF fonts for text rendering  
├── requirements.txt       # Python dependencies  
└── README.md              # This file  

---

## 🧰 Installation  

### 1. Requirements  
- Raspberry Pi OS (Bookworm or Bullseye recommended)  
- Python 3.9 or newer  
- RGBMatrix hardware (HUB75 panel + adapter board)

### 2. Setup  
```bash
sudo apt update
sudo apt install python3-pip python3-dev git
git clone https://github.com/Max6025/forgex-matrix-64x64.git
cd forgex-matrix-64x64
pip3 install -r requirements.txt
```

### 3. Start  
```bash
sudo python3 matrix.py
```

🧩 The script will **automatically create a `config.ini` file** if it does not exist.  
You can adjust all parameters inside it after the first start.

To start automatically on boot, add it to `/etc/rc.local` or create a systemd service.

---

## ⚙️ Configuration (`config.ini`)

Example excerpt:

```ini
[api]
printer_ip = 192.168.1.192
printer_port = 7125
api_interval = 2.0

[matrix]
rows = 64
cols = 64
brightness = 60
```

---

## 💡 Simulation Mode  

You can run a fully interactive simulation without connecting to a printer:

```bash
python3 matrix.py
```

Then in the console, use:
```
SIM> printing
SIM> paused
SIM> complete
SIM> error
SIM> autocycle
```

---

## 🧠 Announcement System  

You can display scrolling or centered messages from a simple text file:

```bash
echo "Important Maintenance Message" > /home/pi/announcement.txt
```

---

## 🧾 Logging  

All debug events are written to:  
```
/var/log/matrix64/api.log
```

Enable or disable logs in `config.ini`:
```ini
[general]
debug_enabled = true
```

---

## 🧑‍💻 Author  

**[Max6025](https://github.com/Max6025)**  
🔗 GitHub: [https://github.com/Max6025](https://github.com/Max6025)

---

## 🧾 License  

This project is licensed under the **MIT License**.  
See [LICENSE](LICENSE) for details.

---

## ⭐ Credits  

Developed with ❤️ by **[Max6025](https://github.com/Max6025)**  
Special thanks to the **rpi-rgb-led-matrix** project for the rendering backend.

---

> “The simplest status display — beautifully animated.”  
> — *Max6025, 2025*
