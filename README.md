# Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models


This is the official repository for the paper **"Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models"**.

### Feixiang Liu, Xiaohui Li, Wenhui Gao, Jiaqing Xiong, Guanchong Niu and Chung Shue Chen

#### Xidian University，China
#### Nokia Bell Labs，France

### Framework Architecture

Our model introduces a novel fusion module, knowledge transfer, and a foundation model to significantly improve performance over existing approaches. The architecture is built on a teacher-student design with dedicated modules for temporal modeling and multimodal fusion.

<p align="center">
  <img src="photos/MSETframework.png" alt="Detailed Framework Overview" width="720"><br>
  <em>Figure: Overview of the proposed framework.</em>
</p>

<p align="center">
  <img src="photos/TACA.png" alt="Detailed Framework Overview" width="720"><br>
  <em>Figure: The TACA fusion module.</em>
</p>

### Setup

Experiments are conducted on the DeepSense 6G dataset.

| Experimental Setup | Dataset Scenarios |
| :---: | :---: |
| ![Experimental Setup](photos/Scene.png) | ![Dataset Scenarios](photos/Scene1-8.png) |
| *Figure: Data collection platform.* | *Figure: Sample V2I scenarios.* |


---

## Experimental Results

### Overall Performance Across Scenarios

Our method ("Ours") consistently outperforms all baselines in Top-k accuracy across eight different real-world scenarios.

![Results Table 1](photos/s1-s4.jpg)
*Table: Performance on Scenarios 1-4.*

![Results Table 2](photos/s5-s8.jpg)
*Table: Performance on Scenarios 5-8.*

### Task-Specific Performance

The model shows state-of-the-art performance when scenarios are grouped into more challenging, specific tasks.

| Single-Target Task | Multi-Target Task |
| :---: | :---: |
| ![Single-Target Task Results](photos/T1.png) | ![Multi-Target Task Results](photos/T2.png) |
| *Figure: Top-k accuracy (Scenarios 5-8).* | *Figure: Top-k accuracy (Scenarios 1-4).* |

| Nighttime Task | Daytime Task |
| :---: | :---: |
| ![Nighttime Task Results](photos/T3.png) | ![Daytime Task Results](photos/T4.png) |
| *Figure: Top-k accuracy (Scenarios 2, 4, 5).* | *Figure: Top-k accuracy (Scenarios 1, 3, 6, 7, 8).* |

### Error Analysis

Confusion matrices show that prediction errors are overwhelmingly concentrated on beams adjacent to the ground truth, indicating high reliability.

![Confusion Matrices](photos/CONFUSE.png)
*Figure: Row-normalized confusion matrices for beam prediction across the four tasks.*


### TCN Experiments
![Results Table 3](photos/TCN.jpg)
*Table: Temporal ablation on Task 2.*

![Results Table 4](photos/TCN_x.jpg)
*Table: Sensitivity of threshold initialization On Task 2.*

### Why our combination is optimal？

*Table: Performance on Scenarios 1-4.*

*Table: Performance on Scenarios 1-4.*

*Table: Performance on Scenarios 1-4.*


### Protocol
![Protocol](photos/Protocols.png)

*Figure: MSET-Assisted Beam Search and Tracking Protocol.*

---

## Code

Code coming soon.


