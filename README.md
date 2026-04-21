# 🐈‍⬛ PiCat: The Raspberry Pi Robotic Cat

![PiCat Cover Image](Media/picat_cover.jpg)

**PiCat** is an advanced, open-source quadruped robotic cat built for a university project. It is based on the Freenove Robot Dog kit architecture but customized into a feline form factor. The project integrates hardware engineering, real-time control via Python, and cross-platform remote operation.

---

## 📥 Quick Download (Ready to Run)
If you want to start controlling **PiCat** immediately without setting up the source code environment, download the pre-compiled applications:

* **📱 Mobile App (Android):** [Download PiCat_Controller.apk](Apps/Mobile/PiCat_Controller.apk)
* **💻 Desktop Controller (Windows):** [Download PiCat_Desktop.exe](Apps/PC/PiCat_Desktop.exe)

---

## 🛠️ Hardware Components
* **Controller:** Raspberry Pi (3B+ / 4 Recommended)
* **Shield:** Freenove Robot Shield for Raspberry Pi
* **Actuators:** 13x Servo Motors (Legs and Head movement)
* **Sensors:** Ultrasonic Sensor (Distance), MPU6050 (Balance), Battery Voltage Monitor (ADC)
* **Power:** 2x 18650 Li-ion Batteries

---

## 📂 Repository Structure
We have organized the repository to be clean and modular, focusing on the essential files for operation:

```text
PiCat/
├── Apps/                       # Pre-compiled binaries for immediate use
│   ├── Mobile/                 # Android APK
│   └── PC/                     # Windows Executable
├── Code/                       # Source Code
│   ├── Server/                 # Python code running on the Raspberry Pi
│   │   ├── main.py             # Main Entry Point
│   │   ├── Action.py           # Movement Sequences (Walk, Sit, etc.)
│   │   ├── Control.py          # Logic for processing Client commands
│   │   ├── PCA9685.py          # PWM Driver for Servos
│   │   └── Ultrasonic.py       # Distance sensing logic
│   └── Client/                 # Source code for PC/Mobile interfaces
├── Media/                      # Project images, videos, and diagrams
├── Docs/                       # University reports and assembly guides
└── README.md                   # Project documentation
```
---

## 🚀 Installation & Setup

* **1.Clone the Repo:**
```bash
git clone [https://github.com/YourUsername/PiCat.git](https://github.com/YourUsername/PiCat.git)
cd PiCat/Code/Server
```
* **2.Automated Library Installation:**
The project requires I2C and specific Python libraries. Run the setup script provided:
```bash
sudo python setup.py
```
Reboot your Raspberry Pi after the script finishes.

---

## 🔧 Assembly & Calibration
**CRITICAL**: Before fully assembling the PiCat frame, you must calibrate the servos to avoid mechanical damage.
**1. Connect servos to the Shield.**
**2. Run the calibration command to set all motors to 90 degrees:**
```bash
python Servo.py 90
```
**3. Attach the legs and frame parts once the servos are locked at 90°.**

---

## 🧪 Module Testing
Before running the full system, test each hardware unit individually:

* Test Ultrasonic: ```bash sudo python Ultrasonic.py ```

* Test Servos: ```bash sudo python Servo.py ```

* Test Battery: ```bash sudo python ADS7830.py ```

---

