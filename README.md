# MQTT-Based Light Control System

An interactive web application designed for IoT light control using the MQTT protocol. This project features a web interface with a dynamic light bulb simulation and a Python script that acts as a virtual IoT device responding to MQTT commands.

![Demo](https://via.placeholder.com/800x400?text=MQTT+Light+Control+Demo)

## Key Features

- User-friendly web interface with animated light bulb effects
- Real-time MQTT-based communication
- ON/OFF controls with immediate visual response
- Adjustable brightness control
- Python-based simulated IoT device

## Project Structure

- **`index.html`**: Provides the web-based UI for controlling the light
- **`light_simulation.py`**: Python script emulating an IoT device
- **`README.md`**: Documentation for setup and usage

## Technical Overview

- Uses MQTT.js for WebSockets-based MQTT communication in the browser
- Utilizes Paho MQTT for Python-based device simulation
- Connects to the MQTT broker at `157.173.101.159`
- Publishes commands to `/student_group/light_control`
- Subscribes to `/student_group/light_status` for updates

## Installation & Setup

### Prerequisites

- A modern web browser with JavaScript enabled
- Python 3.x with `paho-mqtt` installed
- Connectivity to the MQTT broker at `157.173.101.159`

### Running the Web Interface

1. Open `index.html` in a browser.
2. The UI will attempt to connect to the MQTT broker over WebSockets (port 9001).
3. Use the provided buttons to toggle the light ON or OFF and adjust brightness.

### Running the Python IoT Simulation

1. Install dependencies:
   ```bash
   pip install paho-mqtt
   ```
2. Start the simulation script:
   ```bash
   python light_simulation.py
   ```
3. The script will connect to the MQTT broker (port 1883) and react to commands.

## MQTT Topics Used

- `/student_group/light_control` – Transmits ON/OFF commands to the device
- `/student_group/light_status` – Receives feedback on the current light status

## Workflow Explanation

1. The web app sends ON/OFF commands to `/student_group/light_control`.
2. The Python script listens for these messages and acts accordingly.
3. The script sends status updates to `/student_group/light_status`.
4. The UI updates the light bulb animation based on received feedback.

## Troubleshooting Guide

- If the web app fails to connect, verify the MQTT broker’s availability.
- Ensure port 9001 is accessible for WebSockets communication.
- Ensure port 1883 is open for Python MQTT connections.
- Check browser console logs for potential connection issues.

## License

Distributed under the [MIT License](LICENSE).

## Credits

- MQTT.js for browser-based MQTT handling
- Paho MQTT for Python-based client operations
