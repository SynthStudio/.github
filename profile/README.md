# SynthStudio

<div align="center">
  <img src="docs/images/synthstudio_logo_placeholder.png" alt="SynthStudio Logo" width="400"/>
  <p><em>A high-performance simulation framework for synthetic data generation and computer vision development</em></p>
</div>

https://github.com/user-attachments/assets/86fa7057-e6e0-421e-b0d4-7857b56a058d

## Overview

SynthStudio is an advanced simulation framework designed for generating high-fidelity synthetic data for computer vision, reinforcement learning, and robotics applications. Built with a focus on performance and realism, SynthStudio provides a complete environment for:

- Creating realistic physical simulations with accurate lighting
- Generating synthetic training data for computer vision algorithms
- Benchmarking and testing reinforcement learning agents
- Developing and validating drone navigation and control systems

While initially focused on drone simulations, the architecture is designed to be extensible to other vehicles and use cases.

![SynthStudio GUI Placeholder](docs/images/synthstudio_gui_placeholder.png)

## Architecture

SynthStudio is built on three core components that work together to provide a comprehensive simulation environment:

### 1. Frontend GUI

The interactive frontend provides a development environment for:

- Configuring and controlling simulations
- Capturing and replaying motion sequences
- Real-time debugging of entity properties
- Visualizing multiple viewports and camera perspectives
- Adjusting simulation parameters on the fly

Built with Dear ImGui, the GUI offers a lightweight but powerful interface that allows developers to interact with all aspects of the simulation.

### 2. Backend ECS Core

At the heart of SynthStudio is a high-performance Entity-Component-System (ECS) architecture:

- **Entities**: Represent objects in the simulation (drones, obstacles, cameras)
- **Components**: Store data for entities (transforms, physics properties, renderers)
- **Systems**: Process entities with specific components (physics, rendering, control)

Key systems include:

- **Rendering System**: GPU-accelerated OpenGL rendering with CUDA integration
- **Physics System**: Realistic physics simulation for object interactions
- **Transform System**: Hierarchical scene graph for entity relationships
- **Camera System**: Multiple viewports and camera types (free, drone, sensor)
- **Controller System**: Input handling for manual control and testing
- **Recorder System**: Capture and replay motion sequences

### 3. Python Integration Adapter

SynthStudio features a zero-copy integration layer with Python:

- Shared memory interface via memory-mapped files in `/dev/shm`
- Direct GPU memory access using CUDA interoperability
- Real-time streaming of camera viewports to Python processes
- Bidirectional communication of entity transforms and properties

This allows external Python processes to:
- Access simulation data without performance overhead
- Run computer vision algorithms on synthetic camera feeds
- Implement reinforcement learning agents that interact with the simulation
- Validate algorithms against recorded ground truth

![Python Integration Diagram Placeholder](docs/images/python_integration_placeholder.png)

## Example Use Case: Monocular SLAM Evaluation

The following example demonstrates how SynthStudio can be used to evaluate a monocular SLAM pipeline:

1. Configure a drone with camera sensors in the simulation
2. Record a flight path with ground truth poses
3. Stream synthetic camera frames to Python via shared memory
4. Run a SLAM algorithm on the synthetic frames
5. Compare estimated poses against ground truth for quantitative evaluation

![SLAM Evaluation Placeholder](docs/images/slam_evaluation_placeholder.png)

## Features

- **Photorealistic Rendering**: PBR materials, realistic lighting, and advanced shading
- **Physics Simulation**: Accurate collision detection and physical interactions
- **Multiple Camera Types**: Configurable sensors with realistic parameters
- **Motion Recording**: Capture and replay entity movements and transformations
- **Zero-Copy Python Integration**: Direct GPU memory access for external processing
- **Extensible Entity System**: Easily add new entities, components, and systems
- **Performance Optimized**: Designed for real-time simulation with minimal allocations

## Getting Started

(Coming soon: Installation instructions, basic usage examples, and API documentation)
