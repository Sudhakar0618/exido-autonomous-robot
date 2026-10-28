# EXIDO: AI-Powered Autonomous Mobile Robot

## Project Overview
EXIDO is an advanced autonomous mobile robot designed for real-time object detection, obstacle avoidance, and smart navigation in complex environments and disaster scenarios. It bridges the gap between autonomous movement and computer vision.

---

## Hardware Components & Specifications
* **Edge AI Computer:** NVIDIA Jetson Nano / Raspberry Pi 4 (Handles high-level perception and AI inference).
* **Microcontroller:** ESP32 / Arduino Mega (Handles low-level motor control and sensor reading).
* **Camera:** HD USB/CSI Camera (Provides real-time video feed for computer vision).
* **Sensors:** 2D LiDAR / Ultrasonic & ToF Sensors (For obstacle detection and distance estimation).
* **Mobility:** L298N Motor Driver with a robust 4WD/6WD Chassis.

---

## System Architecture & Connections
* **Perception Layer:** The camera captures live video processed via YOLO models for object and person detection.
* **Navigation & SLAM:** Runs 2D grid mapping and path planning for autonomous movement toward a target.
* **Control & Actuation:** The edge computer sends high-level commands to the microcontroller, which translates them into PWM signals for the motor drivers.

---

## Simulation Setup & Instructions
To test the navigation and vision pipeline in a virtual environment:

1. **Prerequisites:** ROS (Robot Operating System), Gazebo Simulator, Python 3.8+, and Ultralytics YOLO.
2. **Commands:**
   ```bash
   git clone [https://github.com/Sudhakar0618/exido-autonomous-robot.git](https://github.com/Sudhakar0618/exido-autonomous-robot.git)
   cd exido-autonomous-robot
   pip install -r requirements.txt
   roslaunch exido_sim robot_world.launch
   python3 src/navigation_node.py
