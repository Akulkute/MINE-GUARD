# MINE-GUARD
# MineGuard: IoT Miner Safety System

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)
![Platform](https://img.shields.io/badge/platform-IoT%20%7C%20Web%20%7C%20Mobile-orange)

MineGuard is an end-to-end IoT safety ecosystem designed to monitor environmental hazards and tracking metrics in underground mining environments. By combining real-time sensor data with predictive analytics, MineGuard helps prevent accidents, tracks miner locations, and ensures swift emergency responses.

---

## 🚀 Features

*   **Real-Time Hazard Detection:** Continuous monitoring of toxic gases (CO, $CH_4$), temperature, humidity, and air quality.
*   **Miner Health Tracking:** Wearable integration to track heart rate, body temperature, and SpO2.
*   **Geofencing & Localization:** BLE/UWB-based indoor positioning to track miners within underground tunnels.
*   **Predictive Alerts:** Machine learning models running at the edge/cloud to predict structural collapses or hazardous gas build-ups before they reach critical levels.
*   **SOS & Emergency Broadcast:** A physical panic button on the wearable that triggers instant alerts across the central dashboard and audio alarms in the mine.

---

## 🏗️ System Architecture

MineGuard operates on a three-tier architecture:

1.  **Hardware Layer (Edge):** ESP32/ESP-01-based wearable nodes and fixed anchor stations equipped with sensors (MQ-9, MQ-135, LM35,MAX30105).
2.  **Network Layer:** ESP NOW / Mesh Wi-Fi protocol ensuring reliable data transmission through thick underground structures to the surface gateway.
3.  **Application Layer:** A centralized Node.js/Python backend paired with a React/Next.js dashboard for real-time visualization, SMS/Email alerts (via Twilio), and data logging.

## System is divided in 5 parts
1. **HAND-device:** Track the heart beat and SpO2 readings. As well as it show the visual alerts and can send the SOS alerts from the miner to control room using ESP-01

2. **BACK-device:** It consist of the 3 sensors Temp., MQ-9, MQ-135, LM35 to measure the parameters of the gas inside the tunnel. It also forward the data comming from the hand-device to the repeater-device.

3. **REPEATER-device:** It forward the data coming from the hand & back device to the control room using ESP-now Protocol which gives the range of 100 meters in the tunnel.

4. **CONTROLROOM-device:** It takes the reading from the repeater and process it and can send alerts to the miners. The data is send to the dashboard.

5. **DASHBOARD:** It shows the data of all the miners currently working in the mine and also send the alerts to the miner regarding the SpO2 & Temp. levels.
---

## 🛠️ Tech Stack

### Hardware & Firmware
*   **Microcontrollers:** ESP32, ESP-01 IoT
*   **Communication:** ESP-NOW, WIFI
*   **Sensors:** MQ-9 (Methane), MQ-135 (Carbon Monoxide), LM35 (Temp/Humidity), MAX30105(SpO2)

### Backend & AI
*   **Runtime:** Node.js / Python 3.10
*   **Framework:** FastAPI / Express.js

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

### Installation

#### 1. Clone the Repository
```bash
git clone [https://github.com/yourusername/mineguard.git](https://github.com/Akulkute/MINE-GUARD.git)
cd mineguard

```

#### 2. Firmware Setup (Hardware)

1. Open `hardware/mineguard_node/mineguard_node.ino` in the Arduino IDE.
2. Install required libraries via the Library Manager: `LM35 sensor library`, `Adafruit MAX30105`, `ESP-NOW`.
3. Configure your Wi-Fi/LoRa credentials in the `config.h` file.
4. Flash the code to your ESP32/ESP-01.

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
