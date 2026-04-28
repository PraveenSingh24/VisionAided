# Vision-Aided Mapless Navigation Framework for Service Robots

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
*(Add any other relevant badges here)*

## Overview
This repository contains the official source code and ROS workspaces for our paper: **"[Insert Your Paper Title Here]"**. 

Our framework proposes a real-time, mapless navigation strategy for autonomous service robots operating in complex physical environments. It dynamically processes RGB-D data without relying on a persistent global SLAM map, utilizing a custom deep-learning perception pipeline to ensure efficient memory usage and reduce redundancy.

To ensure reproducibility and facilitate further research, this repository provides the complete code for both our 3D simulation environments and our physical real-world deployments.

## Hardware & Sensor Integration
The physical experiments in this repository are optimized and deployed on the following hardware:
* **Mobile Base:** Clearpath Husky A200
* **Perception:** RGB-D Sensor (Intel RealSense D455)
* **Compute:** [Insert your onboard compute, e.g., NVIDIA Jetson / Mini-PC]

## Repository Structure
The codebase is divided into two primary workspaces to separate the simulated environments from the physical robot deployment:

### 1. `/Simulation_Workspace`
Contains the ROS packages required to run the navigation framework within a simulated environment (e.g., Gazebo).
* **`/src/[your_perception_pkg]`**: Scripts for the custom perception pipeline (semantic segmentation, point cloud processing).
* **`/src/[your_planning_pkg]`**: The core mapless path-planning algorithms.
* **`/src/vehicle_simulator`**: 3D environments and mesh files for testing. *(Note: Large .dae mesh files are hosted externally at [Link to Drive/HuggingFace if applicable])*

### 2. `/Physical_Husky_Workspace`
Contains the deployment-ready ROS packages specifically tuned for the Clearpath Husky A200.
* **`/src/[your_husky_launch_pkg]`**: Hardware bring-up scripts and sensor node initialization for the RealSense D455.
* **`/src/depth_to_pointcloud`**: Real-time processing nodes for incoming RGB-D frames. *(Note: Large pre-trained .pth model weights are hosted externally at [Link to Drive/HuggingFace])*

## Quick Start & Dependencies
* **OS:** Ubuntu [e.g., 20.04]
* **ROS:** [e.g., Noetic]
* **Deep Learning:** PyTorch `[version]`, CUDA `[version]`

### Building the Workspaces
*(Provide standard `catkin_make` instructions here for reviewers)*
```bash
cd Simulation_Workspace
catkin_make
source devel/setup.bash
