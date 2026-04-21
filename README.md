# 🐈‍⬛ PiCat: The Raspberry Pi Robotic Cat

![PiCat Cover Image](media/picat_cover.jpeg)

**PiCat** is an advanced, quadruped robotic cat built for a university project. It is based on the Freenove Robot Dog kit architecture but customized into a feline form factor. The project integrates hardware engineering, real-time control via Python, and cross-platform remote operation.

---

## 📥 Quick Download (Ready to Run)
If you want to start controlling **PiCat** immediately without setting up the source code environment, download the pre-compiled applications:

* **📱 Mobile App (Android):** [Download PiCat_Controller.apk](Apps/Mobile/PiCat_Controller.apk)
* **💻 Desktop Controller (Windows):** [Download PiCat_Desktop.exe](Apps/PC/PiCat_Desktop.exe)

---

## 🌟 Features & Functions
PiCat is packed with dynamic movements and smart capabilities powered by the Raspberry Pi and onboard sensors.

### 🦾 Kinematic Features (Movements)
The robot's 13 degrees of freedom allow it to move fluidly like a real animal.

![PiCat Features](media/features.webp)

* **Crawling & Walking:** Omni-directional walking capabilities.
* **Posture Adjustment:** Move the body up, down, forward, and backward while the paws stay firmly planted.
* **3D Twisting:** Roll, pitch, and yaw body twists to simulate feline flexibility.

### 🧠 Smart Functions (Sensors & AI)
Beyond basic movements, PiCat can interact with its environment.

![PiCat Functions](media/functions.webp)

* **Self-Balancing:** Uses the MPU6050 Gyroscope/Accelerometer to maintain stability on uneven surfaces.
* **Computer Vision:** Capable of Face Recognition and Object/Color Tracking (e.g., tracing a red ball) using OpenCV.
* **Real-Time Video:** Streams live camera feed directly to the control client.
* **Distance Measurement:** Uses the Ultrasonic sensor to detect obstacles (up to 10cm accuracy).
* **Interactive Feedback:** Features programmable RGB LEDs for status indication and a Buzzer for audio alerts.
* **Head Articulation:** Multi-axis head movements (look up, down, left, right).
* **Cross-Platform Client:** Fully controllable via PC GUI or Mobile App over Wi-Fi.

---

## 🛠️ Hardware Components

![hardware components](media/hardware components.jpg)

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

## 🎮 How to Control PiCat
PiCat operates on a Client-Server architecture.
**1. Start the Server (The Cat)**
Run the following on your Raspberry Pi:
```bash
sudo python main.py
 ```
The server will start and display the IP address of the Pi.

**2. Connect the Client (Remote)**
* **Via PC:** Open the PC GUI, enter the Pi's IP address, and click Connect.

* **Via Mobile:** Open the PiCat App, enter the IP, and use the on-screen joysticks to move.

---

## 🤝 Acknowledgments
* Inspired by the Freenove Robot Dog Kit.
* Developed as a University Project for sustainable robotics exploration.
