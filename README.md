# MINE-GUARD
# MineGuard: IoT & AI-Powered Miner Safety System

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)
![Platform](https://img.shields.io/badge/platform-IoT%20%7C%20Web%20%7C%20Mobile-orange)

MineGuard is an end-to-end IoT and AI-driven safety ecosystem designed to monitor environmental hazards and tracking metrics in underground mining environments. By combining real-time sensor data with predictive analytics, MineGuard helps prevent accidents, tracks miner locations, and ensures swift emergency responses.

---

## 🚀 Features

*   **Real-Time Hazard Detection:** Continuous monitoring of toxic gases (CO, $CH_4$), temperature, humidity, and air quality.
*   **Miner Health Tracking:** Wearable integration to track heart rate, body temperature, and detect sudden falls (via accelerometer/gyroscope).
*   **Geofencing & Localization:** BLE/UWB-based indoor positioning to track miners within underground tunnels.
*   **AI Predictive Alerts:** Machine learning models running at the edge/cloud to predict structural collapses or hazardous gas build-ups before they reach critical levels.
*   **SOS & Emergency Broadcast:** A physical panic button on the wearable that triggers instant alerts across the central dashboard and audio alarms in the mine.

---

## 🏗️ System Architecture

MineGuard operates on a three-tier architecture:

1.  **Hardware Layer (Edge):** ESP32/Arduino-based wearable nodes and fixed anchor stations equipped with sensors (MQ-4, MQ-7, DHT22, MPU6050).
2.  **Network Layer:** LoRaWAN / Mesh Wi-Fi protocol ensuring reliable data transmission through thick underground structures to the surface gateway.
3.  **Application Layer:** A centralized Node.js/Python backend paired with a React/Next.js dashboard for real-time visualization, SMS/Email alerts (via Twilio), and data logging.

---

## 🛠️ Tech Stack

### Hardware & Firmware
*   **Microcontrollers:** ESP32, Arduino Nano IoT
*   **Communication:** LoRaWAN (RFM95W), BLE (Bluetooth Low Energy)
*   **Sensors:** MQ-4 (Methane), MQ-7 (Carbon Monoxide), DHT22 (Temp/Humidity), MPU6050 (Fall Detection)

### Backend & AI
*   **Runtime:** Node.js / Python 3.10
*   **Framework:** FastAPI / Express.js
*   **Database:** InfluxDB (Time-series sensor data), MongoDB (User & Device logs)
*   **ML Framework:** TensorFlow Lite (for edge anomaly detection)

### Frontend
*   **Framework:** React.js / Tailwind CSS
*   **Maps & Charts:** Leaflet.js (Indoor Mapping), Chart.js (Real-time analytics)

---

## 📦 Getting Started

### Prerequisites

Before setting up the project, ensure you have the following installed:
*   [Arduino IDE](https://www.arduino.cc/en/software) (for hardware firmware)
*   [Node.js](https://nodejs.org/) (v18 or higher)
*   [Python](https://www.python.org/) (v3.10 or higher)
*   [Docker](https://www.docker.com/) (Optional, for easy database deployment)

### Installation

#### 1. Clone the Repository
```bash
git clone [https://github.com/yourusername/mineguard.git](https://github.com/yourusername/mineguard.git)
cd mineguard

```

#### 2. Firmware Setup (Hardware)

1. Open `hardware/mineguard_node/mineguard_node.ino` in the Arduino IDE.
2. Install required libraries via the Library Manager: `DHT sensor library`, `Adafruit MPU6050`, `LoRa`.
3. Configure your Wi-Fi/LoRa credentials in the `config.h` file.
4. Flash the code to your ESP32/Arduino board.

#### 3. Backend Setup

```bash
cd backend
pip install -r requirements.txt
cp .env.example .env # Update your database and API keys here
python main.py

```

#### 4. Frontend Setup

```bash
cd ../frontend
npm install
npm run dev

```

The dashboard should now be running at `http://localhost:3000`.

---

## 📊 Dashboard Preview

> **Note:** The dashboard includes an interactive 2D grid map of the mine layouts, color-coded hazard zones (Green: Safe, Yellow: Warning, Red: Evacuate), and a live feed of all active miners.

---

## 🤝 Contributing

Contributions make the open-source community an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

```

---

Would you like me to adjust this README to focus on a different type of project, or add specific sections like detailed hardware wiring guides or API endpoint documentation?

```
