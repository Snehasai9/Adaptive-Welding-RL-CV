# 🤖 Adaptive Welding Robot Simulation via CV & RL

An intelligent automation framework bridging physical robotic simulation inside **CoppeliaSim** with Python-based Computer Vision (CV) perception pipelines and Reinforcement Learning (RL) trajectory optimization.

---

## 📺 Project Simulation Demo
🎬 **[Watch the Simulation Video on Google Drive](👉 https://drive.google.com/file/d/17N1l4FzQcp0qfOpyJBGGWPVnkrynlWdV/view?usp=drive_link 👈)**

---

## 🏗️ System Architecture & Data Flow

The project is built around a real-time, closed-loop data pipeline where the perception layer dynamically drives the robotic actuation matrix:

1. **Perception Loop (CNN):** Streams live vision sensor arrays from CoppeliaSim into a custom Convolutional Neural Network trained to perform real-time regression analytics, tracking the dynamic variations of the weld bead width.
2. **Decision Loop (DDPG):** Processes spatial coordinates and geometric dimensions into a continuous numerical state space. A Deep Deterministic Policy Gradient (DDPG) algorithm utilizes an Actor-Critic architecture to map these states directly to continuous robotic joint velocity actions.
3. **Simulation Actuation Interface:** Communicates via Python API bindings to execute fluid, real-time trajectory corrections back into the CoppeliaSim kinematic model.

---

## 🛠️ Technical Highlights & Engineering Depth

### 👁️ Deep Learning & Perception Analytics
* **CNN Architecture:** Developed a Convolutional Neural Network pipeline optimized for coordinate regression to monitor and estimate the weld bead width dynamically under changing simulation perspectives.
* **Array Optimization:** Leveraged **NumPy** for highly vectorized image matrix pre-processing and resizing, minimizing latency before feeding frames into the deep learning model inference loop.

### 🧠 Reinforcement Learning & Continuous Control
* **DDPG Framework:** Implemented a Deep Deterministic Policy Gradient (DDPG) agent, leveraging its dual Actor-Critic architecture to solve the complex high-dimensional continuous action control space required for multi-joint robotic arms.
* **Reward Function Design:** Engineered a tailored continuous reward function that evaluates real-time bead dimensions, penalizes significant deviations from the target track, and minimizes high angular accelerations to prevent jerky physical transitions.

### 💻 Script Integration & Simulation Loop
* **Direct Pipeline Execution:** Combined the entire process into a single, functional Python script that sequentially captures simulation frames, feeds them into the CNN to predict bead width, and passes the output straight to the DDPG control loop.
* **Simulator Interfacing:** Leveraged standard CoppeliaSim Python API bindings to directly stream live sensor data out of the simulator and send joint velocity commands back to the robotic arm.

---
## 🎓 Project Details
* **Project Type:** 3rd-Year Mechanical Engineering Project
* **Core Technologies:** CoppeliaSim, Python, CNN (Perception), DDPG (Control Loop)
