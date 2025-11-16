# MSET: Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models


This is the official repository for the paper **"Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models"**.

### Feixiang Liu, Xiaohui Li, Wenhui Gao, Jiaqing Xiong, Guanchong Niu and Chung Shue Chen

#### Xidian University，China
#### Nokia Bell Labs，France

---

### Framework Architecture

MSET is a lightweight, efficient multimodal beam prediction framework tailored for real-world scenarios. It combines visual semantics, temporal modeling, and positional priors to achieve robust performance in complex and dynamic V2I environments.

<p align="center">
  <img src="photos/MSETframework.png" alt="Detailed Framework Overview" width="720"><br>
  <em>Figure: Overview of the proposed MSET framework.</em>
</p>

<p align="center">
  <img src="photos/TACA.png" alt="Detailed Framework Overview" width="720"><br>
  <em>Figure: The TACA fusion module.</em>
</p>

---

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
##### Temporal ablation (Table Left)

To isolate the effect of the depth gate, we keep the temporal stack (kernel size, dilations, and number of layers) fixed and only change the receptive-field mechanism. Compared with the fixed receptive-field baseline, a fixed-depth gate brings only modest improvements in Top-1/Top-5 and power loss. In contrast, the proposed volatility-driven gate achieves clearly higher Top-1/Top-5 accuracy and lower power loss **with identical temporal complexity**, showing that conditioning the gate on motion volatility is substantially more effective than a static pattern.

##### Threshold sensitivity (Table Right)

We further study the sensitivity of the volatility-driven gate to the initialization of its thresholds. Across three representative initialization schemes — **Init-A** (narrow linear ramp), **Init-B** (wider linear ramp), and **Init-C** (Init-A plus small Gaussian noise) — the final Top-1/Top-5 accuracy and power loss remain very close, and the learned thresholds stay ordered and monotone in depth. This indicates that the volatility-driven TCN is **robust to reasonable threshold initializations** and consistently outperforms the fixed receptive-field baseline.


<p align="center">
  <img src="photos/TCN.jpg" alt="Results Table 3" width="400" />
  <img src="photos/TCN_x.jpg" alt="Results Table 4" width="400" />
</p>

<p align="center">
  <em>Left: Temporal ablation on Task 2. &nbsp; Right: Sensitivity of threshold initialization on Task 2.</em>
</p>

### Why our combination is optimal？

<p align="center">
  <img src="photos/swin.png" alt="Swin" width="80%" />
  <br>
  <em>Swin</em>
</p>

<p align="center">
  <img src="photos/res.png" alt="Res" width="80%" />
  <br>
  <em>Res</em>
</p>

<p align="center">
  <img src="photos/mamba.png" alt="Mamba" width="80%" />
  <br>
  <em>Mamba</em>
</p>

### Knowledge distillation experiment

<p align="center">
  <img src="photos/KD.png" alt="KD" width="80%" />
  <br>
  <em>KD</em>
</p>

### Protocol
<p align="center">
  <img src="photos/Protocols.png" alt="Protocol." width="720"><br>
  <em>*Figure: MSET-Assisted Beam Search and Tracking Protocol.*</em>
</p>

---

## Code

Our code is coming soon...

