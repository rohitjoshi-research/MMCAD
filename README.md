
---

# MMCA-Detect: Multi-Modal Cross-Attention for Adversarial Attack Detection

## Overview

MMCA-Detect is a proposed defense architecture designed to detect adversarial attacks on the perception systems of Level 4 and 5 autonomous vehicles (AVs). Because existing defenses usually focus on a single sensor, they leave multi-sensor vehicles vulnerable to coordinated attacks. This project introduces a system that fuses camera, LiDAR, and radar data to identify malicious input modifications that might cause an autonomous vehicle to misclassify objects or miss obstacles.

## Key Features

* **Multi-Modal Fusion**: Defends autonomous systems by jointly analyzing camera, LiDAR, and radar data rather than relying on a single sensor.


* **Cross-Attention Mechanism**: Replaces standard feature concatenation with a learned cross-modal attention module that actively searches for inconsistencies between different sensor inputs.


* **Real-Time Design Targets**: Built with the theoretical goal of achieving inference latency below 50 ms to meet automotive safety constraints, though this remains to be tested on actual vehicle hardware.


* **Theoretical Grounding**: Backed by mathematical bounds on detection probability and formal computational complexity analyses.



## Architecture Breakdown

* **Feature Extraction**: The system uses separate encoders to process different sensor types, standardizing them into shared-dimension embeddings.


* **Cross-Modal Attention Fusion**: A multi-head cross-attention layer compares the features from all modalities to derive a cross-modal inconsistency score.


* **Detection Head**: The fused data is passed through a lightweight Multi-Layer Perceptron (MLP) to output a final binary decision (0 for clean, 1 for adversarial).



## Current Validation Status & Results

* **Important Notice**: The current implementation represents a synthetic-data feasibility study, not a real-world validation.


* **Testing Method**: The code pipeline has been successfully tested using synthetic proxy tensors to ensure the training and evaluation logic functions correctly end-to-end.


* **Initial Findings**: On this controlled synthetic task, the full cross-attention model achieved a 96.4% True Positive Rate (TPR) and a 19.6% False Positive Rate (FPR).


* **Future Roadmap**: Future work requires validating the architecture on real driving datasets (like KITTI, nuScenes, and Waymo Open) and measuring actual latency on automotive-grade hardware like the NVIDIA Drive AGX Orin.



---
