# Kinova_Mico2-ROS-LLM-Integration-ROS-MCP-Server.
This project demonstrates a ROS-based pick-and-stack robotic system using the Kinova Mico 2 robotic arm, where high-level task planning is handled using a Claude Large Language Model (LLM).  The robot autonomously performs pick and stacking operations using natural-language, ros-mcp-server and executing them through a ROS control pipeline.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e81f9fd3-3f54-4f9f-b66c-5493b3eca841" />

Project Overview:
The Kinova Mico 2 robot performs sequential pick and stack operations
A Claude LLM is used for:
Task interpretation
Action sequencing
High-level decision making
Low-level motion execution is handled using ROS and MoveIt
The entire pipeline is tested and validated in simulation and execution

![Kinova_ROS-MCP-Server-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/98e0aae6-8d14-4ec5-bee7-a16e56e0ef78)

This project highlights the integration of LLMs with classical robotics motion planning.

Tools & Technologies Used:
Robotics & Simulation
ROS (Robot Operating System)
MoveIt – motion planning and execution
Gazebo – simulation environment
Kinova Mico 2 SDK
Gazebo Link Attacher Plugin – grasp simulation

![Kinova_ROS-MCP-Server-ezgif com-video-to-gif-converter (1)](https://github.com/user-attachments/assets/bad409f6-6287-4a82-8a7d-af2647054a04)


AI & LLM Integration:
Claude Large Language Model
Natural language → structured robot commands
High-level task planning logic

Programming & Middleware:
Python
ROS nodes, services, and publishers
TF frames and coordinate transformations
Custom service-based pick & place pipeline

System Tools:
Linux (Ubuntu)
Git & GitHub

System Architecture (High Level):
User provides a natural language instruction
Claude LLM interprets the task and generates an action sequence
ROS services translate actions into robot goals
MoveIt plans collision-free trajectories
Kinova Mico 2 executes pick and stack motions
Objects are attached/detached in Gazebo to simulate grasping

Key Highlights:
Integration of LLMs with robotic manipulation
Autonomous task execution without hard-coded sequences
Modular ROS service-based architecture
Demonstrates AI-guided decision making in robotics

Future Improvements:
Vision-based object detection
Real-world deployment with RGB-D camera
Feedback loop from execution to LLM
Multi-object task planning
