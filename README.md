# Hierarchical Threat Modeling of AI-Controlled Cyber-Physical Systems

## Overview

This project presents a multi-phase, learning-centric framework for hierarchical threat modeling in AI-controlled Cyber-Physical Systems (CPS) using the SWaT (Secure Water Treatment) dataset. The framework combines statistical analysis, layer-wise CPS decomposition, feature engineering, AI-driven control simulation, reinforcement learning, and deep learning-based anomaly detection to analyze cyber threats across multiple CPS layers.

The project is designed to study how attacks propagate through interconnected CPS environments and how AI-based systems behave under adversarial conditions.

---

# Project Goals

The primary objectives of this project are:

* Perform hierarchical threat modeling across CPS layers
* Analyze attack surfaces in AI-controlled industrial systems
* Simulate AI-based control loops using PID controllers and PPO reinforcement learning
* Engineer layer-specific CPS features for improved threat analysis
* Detect cyber-attacks using deep learning anomaly detection models
* Study adversarial behavior in industrial control systems
* Evaluate attack impact across physical, network, control, supervisory, and process layers

---

# Dataset

## SWaT Dataset

The project uses the SWaT (Secure Water Treatment) dataset, a widely used industrial control system security dataset containing:

* Normal operational data
* Attack scenario data
* Sensor readings
* Actuator states
* PLC-related signals

The dataset represents a real-world water treatment plant with multiple industrial stages and cyber-physical interactions.

---

# System Architecture

The framework follows a hierarchical multi-phase pipeline:

```text
SWaT Dataset
     │
     ▼
Phase 1 → Data Cleaning + CPS Layer Mapping
     │
     ▼
Phase 2 → Layer-wise Feature Engineering
     │
     ▼
Phase 2A → AI Control Loop Simulation
     │
     ▼
Phase 3 → Deep Learning Detection Engine
     │
     ▼
Phase 4 → Threat Modeling & Risk Analysis
     │
     ▼
Phase 5 → Visualization & Evaluation
     │
     ▼
Phase 6 → Final Integrated Security Assessment
```

---

# CPS Layer Hierarchy

The project decomposes the CPS into five hierarchical layers:

| Layer             | Description                                  |
| ----------------- | -------------------------------------------- |
| Physical Layer    | Sensor readings, flow, pressure, tank levels |
| Network Layer     | Communication-related system interactions    |
| Control Layer     | PLC and actuator control logic               |
| Supervisory Layer | Monitoring and supervisory operations        |
| Process Layer     | End-to-end industrial process behavior       |

This layered architecture enables targeted threat analysis and attack localization.

---

# Phase 1 — Data Preprocessing & Layer Mapping

Notebook: `ctmas-phase1.ipynb`

## Key Tasks

* Loading and validating SWaT Excel datasets
* Cleaning corrupted and inconsistent records
* Standardizing labels
* Creating binary attack labels
* Mapping sensors and actuators into CPS layers
* Performing statistical summaries for each layer
* Generating attack distribution visualizations

## Core Features

* Automated dataset loading
* Layer-wise feature grouping
* Statistical profiling
* Distribution analysis
* Attack frequency visualization

## Outputs

* `swat_clean.csv`
* `swat_scaled.csv`
* `layer_map.json`
* `phase1_config.json`

---

# Phase 2 — LayerRouter & Feature Engineering

Notebook: `ctmas-phase2.ipynb`

## Key Components

### LayerRouter

Routes SWaT features into independent CPS layer views.

### FeatureEngineer

Generates domain-specific engineered features.

## Engineered Features

### Physical Layer

* Rolling mean
* Rolling standard deviation
* Sensor z-scores

### Control Layer

* Actuator transition counts
* State-change frequency

### Network Layer

* Communication variability
* Temporal interaction statistics

### Supervisory Layer

* Monitoring trends
* Supervisory state transitions

### Process Layer

* Process consistency metrics
* Multi-stage interaction patterns

## Outputs

* Layer-specific engineered datasets
* Layer feature statistics
* Derived feature visualizations
* Layer scalers

---

# Phase 2A — AI Control Loop Simulation

Notebook: `ctmas-phase2a.ipynb`

This phase introduces AI-controlled CPS simulation to justify the "AI-Controlled" component of the project.

## Implemented Components

### PID Controllers

Simulates industrial PLC control behavior.

Functions:

* Reads sensor values
* Computes control error
* Produces actuator commands

### PPO Reinforcement Learning Agent

A reinforcement learning environment was created using Gymnasium and Stable-Baselines3.

## RL Features

* Custom CPS environment
* PPO-based control learning
* Reward-driven optimization
* AI-driven control adaptation

## Adversarial Simulation

The framework evaluates:

* Sensor manipulation
* False data injection
* Adversarial disturbances
* Control instability

## Technologies Used

* Gymnasium
* Stable-Baselines3
* PPO Reinforcement Learning
* PID Control Systems

---

# Phase 3 — AI Detection Engine

Notebook: `ctmas-phase3.ipynb`

This phase implements deep learning-based anomaly detection for cyber-attack detection.

## Detection Strategy

Semi-supervised learning:

* Models are trained only on normal operational data
* Attacks are identified using reconstruction or prediction errors

## Implemented Models

### BiLSTM Autoencoder

Used for sequential temporal anomaly detection.

Features:

* Sliding time windows
* Temporal dependency learning
* Reconstruction-based anomaly scoring

### Variational Autoencoder (VAE)

Used for latent-space anomaly representation.

Features:

* Latent variable modeling
* Probabilistic anomaly detection
* Distribution-aware reconstruction

### Temporal Convolutional Network (TCN) Autoencoder

Used for efficient temporal sequence modeling.

Features:

* Dilated temporal convolutions
* Long-range dependency capture
* Sequence reconstruction

## Detection Objectives

* Detect anomalous CPS behavior
* Identify attack propagation patterns
* Analyze layer-wise anomaly severity
* Compare model reconstruction performance

## Technologies Used

* TensorFlow / Keras
* BiLSTM Networks
* Variational Autoencoders
* TCN Architectures
* SHAP Explainability

---

# Threat Modeling Approach

The framework performs hierarchical attack surface analysis using:

* Layer-wise attack categorization
* Sensor and actuator vulnerability mapping
* Threat propagation analysis
* CPS dependency evaluation
* AI control instability analysis

## Threat Categories

The project studies attacks such as:

* Sensor spoofing
* False data injection
* Control manipulation
* Communication tampering
* Process disruption
* Adversarial control instability

---

# Technologies Used

## Programming & Analysis

* Python
* Jupyter Notebook
* Pandas
* NumPy
* SciPy

## Machine Learning & AI

* TensorFlow / Keras
* Stable-Baselines3
* Reinforcement Learning (PPO)
* Deep Learning Autoencoders

## Visualization

* Matplotlib
* Seaborn

## CPS & Security

* SWaT Dataset
* Industrial Control System Security
* Cyber-Physical System Threat Modeling

---

# Repository Structure

```text
.
├── ctmas-phase1.ipynb
├── ctmas-phase2.ipynb
├── ctmas-phase2a.ipynb
├── ctmas-phase3.ipynb
├── ctmas-phase4.ipynb
├── ctmas-phase5.ipynb
├── ctmas-phase6.ipynb
├── layer_map.json
├── phase1_config.json
└── README.md
```

---

# Key Research Contributions

* Hierarchical CPS layer decomposition
* AI-driven control loop simulation
* Integration of reinforcement learning with CPS security
* Multi-model anomaly detection pipeline
* Layer-wise attack surface analysis
* Learning-centric CPS threat modeling

---

# Research Domains

* Cybersecurity
* AI Security
* Industrial Control Systems
* Cyber-Physical Systems (CPS)
* Threat Modeling
* Reinforcement Learning
* Anomaly Detection

---

# Future Work

Potential future improvements include:

* Real-time intrusion response systems
* Online reinforcement learning adaptation
* Graph-based CPS attack modeling
* Federated CPS anomaly detection
* Explainable AI for industrial security
* Multi-agent defensive architectures

---

# Author

**Vedant Jaiswal**

---

# License

This project is intended for academic, research, and educational purposes.
