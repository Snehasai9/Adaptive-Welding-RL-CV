# 🤖 Adaptive Welding Robot Simulation via CV & RL

An intelligent automation framework bridging physical robotic simulation inside **CoppeliaSim** with Python-based Computer Vision (CV) perception pipelines and Reinforcement Learning (RL) trajectory optimization.

---

## 📺 Project Simulation Demo
🎬 **[Watch the Simulation Video on Google Drive](👉 https://drive.google.com/file/d/17N1l4FzQcp0qfOpyJBGGWPVnkrynlWdV/view?usp=drive_link 👈)**

---

## 🏗️ System Architecture & Data Flow

The project is built around a real-time, closed-loop data pipeline where the perception layer dynamically drives the robotic actuation matrix:
1. **Perception Loop (CV):** Streams live Vision sensor arrays from CoppeliaSim. Utilizes OpenCV matrix transformations to filter noise, extract seam profiles, and map precise target paths.
2. **Decision Loop (RL):** Translates pixel/spatial coordinates into a numerical state space. A Deep Reinforcement Learning agent evaluates the state to optimize the torch trajectory while adhering to robotic joint constraints.
3. **Simulation Actuation Interface:** Communicates via Python API bindings to execute fluid, real-time trajectory updates back into the CoppeliaSim kinematic model.

---

## 📊 Results & Performance Analytics

To validate the efficiency of the integrated Computer Vision pipeline and Reinforcement Learning controller, system performance was tracked across iterations:

### 📈 1. Algorithmic Optimization & Reward Convergence
Below is the convergence profile of the Deep RL agent. The upward trend signifies the agent successfully learning the optimal kinematic behaviors while maximizing path alignment and minimizing joint stress penalties.

![RL Reward Convergence](reward_graph.png)

### 📉 2. Path Tracking Accuracy & Minimization of Error
This metric captures the spatial deviation (error margin) between the physical weld seam detected by OpenCV and the actual nozzle path taken by the robotic arm. 

![Tracking Error Minimization](tracking_error.png)

---

## 🛠️ Technical Highlights & Engineering Depth

### 👁️ Computer Vision & Perception Analytics
* **Feature Extraction:** Implemented custom image processing filters (Canny Edge Detection, Hough Line Transforms) to track physical welding lines under varying simulated lighting.
* **Array Optimization:** Leveraged **NumPy** for highly vectorized matrix manipulations, completely avoiding nested Python loops during real-time image coordinate translations.

### 🧠 Reinforcement Learning & Control Logic
* **Reward Function Design:** Engineered a tailored continuous reward function that penalizes path deviation, high angular acceleration, and joint limit saturation.
* **Kinematic Alignment:** Mapped the RL action space directly to the robotic arm's joint velocity controllers to ensure smooth, non-jerky physical transitions.

### 💻 Software Engineering & System Architecture
* **Modular Pipeline Logic:** Divided the system requirements into distinct logical zones (perception, control, simulation data streaming) using Object-Oriented Programming (OOP).
* **Latency Mitigation:** Optimized computation pipelines to achieve minimal latency, ensuring the Python control processing loops remain strictly synchronized with the CoppeliaSim simulator tick rate.

---

## 🎓 Project Details & Academic Credits
* **Project Type:** Independent Course Project
* **Institution:** [Indian Institute of Technology Madras]
* **Project Advisor:** Prof. [Anuj Tiwari]
