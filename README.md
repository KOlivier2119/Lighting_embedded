# MQTT-Powered Smart Light System

An advanced web-based solution for controlling IoT lights via the MQTT protocol. This project includes a user-friendly web interface with a simulated light bulb and a Python script acting as a virtual IoT device that processes MQTT messages.

![Demo](https://via.placeholder.com/800x400?text=MQTT+Light+Control+Demo)

## Main Features

- Intuitive web interface with animated light bulb visuals
- Real-time communication using MQTT
- Toggle light ON/OFF with instant feedback
- Control light brightness
- Python-based virtual IoT device simulation

## Project Structure

- **`index.html`**: Web interface for managing the smart light
- **`light_handling.py`**: Python script simulating an IoT light device
- **`README.md`**: Instructions for installation and usage

## Technical Details

- Implements MQTT.js for WebSockets-based communication in the browser
- Uses Paho MQTT for the Python-based device emulator
- Communicates with the MQTT broker at `157.173.101.159`
- Sends commands to `/student_group/light_control`
- Listens for device status on `/student_group/light_status`

## Setup & Execution

### Requirements

- Modern web browser with JavaScript support
- Python 3.x with the `paho-mqtt` package
- Access to the MQTT broker at `157.173.101.159`

### Starting the Web Interface

1. Open `index.html` in your preferred web browser.
2. The interface will attempt to connect to the MQTT broker via WebSockets (port 9001).
3. Use the buttons to switch the light ON/OFF and adjust the brightness level.

### Running the Python IoT Simulation

1. Install necessary packages:
   ```bash
   pip install paho-mqtt
   ```
2. Run the simulation script:
   ```bash
   python light_simulation.py
   ```
3. The script connects to the MQTT broker on port 1883 and responds to incoming commands.

## MQTT Topics

- `/student_group/light_control` – Handles light ON/OFF and brightness commands
- `/student_group/light_status` – Receives and updates the light's current state

## System Workflow

1. The web application publishes ON/OFF and brightness commands to `/student_group/light_control`.
2. The Python-based IoT device listens and adjusts the light accordingly.
3. The IoT device sends status feedback to `/student_group/light_status`.
4. The UI updates dynamically based on the received status messages.

## Troubleshooting

- Ensure the MQTT broker is operational and accepting connections.
- Verify port 9001 is open for WebSockets and port 1883 for standard MQTT communication.
- Check browser console logs for connection errors.

## License

Distributed under the [MIT License](LICENSE).

## Acknowledgments

- MQTT.js for handling MQTT in the browser
- Paho MQTT for enabling Python-based MQTT operations
