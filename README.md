# Kinova_Mico2-ROS-LLM-Integration-ROS-MCP-Server.
This project demonstrates a ROS-based pick-and-stack robotic system using the Kinova Mico 2 robotic arm, where high-level task planning is handled using a Claude Large Language Model (LLM).  The robot autonomously performs pick and stacking operations using natural-language, ros-mcp-server and executing them through a ROS control pipeline.

## ROS MCP Server – Concept and Role

This project leverages the **ROS MCP Server** as a bridge between a Large Language Model (LLM) and the ROS ecosystem.

The ROS MCP (Model Context Protocol) Server enables an LLM to:
- Discover available robot capabilities
- Call ROS services and actions dynamically
- Execute robot tasks through structured, tool-based interactions

Instead of hard-coding task logic, the MCP server exposes robot functionalities as callable tools, allowing the LLM to reason, plan, and execute actions in a modular and scalable way.

In this project, the ROS MCP Server plays a key role in:
- Translating natural-language task instructions into ROS-level actions
- Orchestrating pick-and-stack sequences dynamically
- Enabling high-level autonomy while keeping low-level motion planning within ROS and MoveIt

This architecture allows classical robotics pipelines to be controlled by modern LLM-based reasoning without modifying core ROS components.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e81f9fd3-3f54-4f9f-b66c-5493b3eca841" />

## Project Overview:
- The Kinova Mico 2 robot performs sequential pick and stack operations
- A Claude LLM is used for:
- Task interpretation
- Action sequencing
- High-level decision making
- Low-level motion execution is handled using ROS and MoveIt
- The entire pipeline is tested and validated in simulation and execution

![Kinova_ROS-MCP-Server-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/98e0aae6-8d14-4ec5-bee7-a16e56e0ef78)

## This project highlights the integration of LLMs with classical robotics motion planning.

## Tools & Technologies Used:
- Robotics & Simulation
- ROS (Robot Operating System)
- MoveIt – motion planning and execution
- Gazebo – simulation environment
- Kinova Mico 2 SDK
- Gazebo Link Attacher Plugin – grasp simulation
- **ROS MCP Server** – LLM to ROS interface

![Kinova_ROS-MCP-Server-ezgif com-video-to-gif-converter (1)](https://github.com/user-attachments/assets/bad409f6-6287-4a82-8a7d-af2647054a04)


## Programming & Middleware:
- Python
- ROS nodes, services, and publishers
- TF frames and coordinate transformations
- Custom service-based pick & place pipeline

## System Tools:
- Linux (Ubuntu)
- Git & GitHub

## System Architecture (High Level)
1. User provides a natural language instruction
2. Claude LLM interprets the task using reasoning and planning
3. The LLM communicates with the **ROS MCP Server**
4. ROS MCP Server exposes robot actions as callable tools
5. ROS services translate actions into robot motion goals
6. MoveIt plans collision-free trajectories
7. Kinova Mico 2 executes pick and stack motions
8. Objects are attached/detached in Gazebo to simulate grasping


## Key Highlights:
- Integration of LLMs with robotic manipulation
- Autonomous task execution without hard-coded sequences
- Modular ROS service-based architecture
- Demonstrates AI-guided decision making in robotics

## Future Improvements:
- Vision-based object detection
- Real-world deployment with RGB-D camera
- Feedback loop from execution to LLM
- Multi-object task planning

## Hardware Deployment and Updates

![Hardwaresetup1-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/a4a097f5-2aa8-424f-a31b-9038796b68ba)

## 👁️ Vision System & Eye-to-Hand Calibration

The system incorporates a **vision-guided manipulation pipeline** using an external RGB-D camera setup (eye-to-hand configuration).

### 📷 Camera Setup
- Intel RealSense depth camera mounted externally (top/side view)
- Provides full workspace visibility for object detection and tracking
- Camera frame is calibrated relative to the robot base frame

### 📐 Eye-to-Hand Calibration
- Implemented **Aruco marker-based calibration**
- Solved **hand–eye calibration problem (AX = XB)** to compute transformation between:
  - Camera frame
  - Robot base frame
- Enabled accurate mapping from image coordinates → robot coordinates

### 🔍 Perception Pipeline
- RGB-D data used for:
  - Object detection and segmentation
  - Depth-based localization
  - 3D coordinate extraction
- Coordinate transformations handled using **ROS TF**

📌 This enables precise vision-guided pick-and-place operations in a structured workspace.

## 🧠 Machine Vision Pipeline

The perception system processes visual input to generate actionable robot commands.

### Pipeline Steps:
1. Capture RGB-D data from Intel RealSense
2. Detect objects using color/geometry-based segmentation
3. Estimate object pose (x, y, z) in camera frame
4. Transform coordinates to robot base frame using TF
5. Generate grasp poses for manipulation

### Key Features:
- Real-time object localization
- Depth-based accuracy for manipulation
- Robust to varying object positions
- Integrated with motion planning pipeline

## 🌍 Toward Real-World Deployment

The system is designed to transition from simulation to real-world environments by:

- Integrating RGB-D camera-based perception
- Enabling vision-guided manipulation
- Supporting dynamic object localization
- Maintaining safety through workspace constraints

Future work includes:
- Real-time object detection using deep learning (YOLO)
- Multi-camera perception setup (top + side view)
- Improved grasp planning for complex objects

## Acknowledgements

This project builds upon the **ROS MCP Server** developed by the Robot MCP community.

- 🔗 ROS MCP Server Repository:  
  https://github.com/robotmcp/ros-mcp-server
  
The ROS MCP Server was integrated and adapted to work with the Kinova Mico 2 pick-and-stack pipeline used in this project.


## 👤 Author

Vaasantha Sri Surya
Computer Science Engineer | Mechatronics Background
Interested in Embedded Systems, Robotics, and AI

🔗 LinkedIn: www.linkedin.com/in/vaasantha-sri-surya-kalidindi-3ba72333a
