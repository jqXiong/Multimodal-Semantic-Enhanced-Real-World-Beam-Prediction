# Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models
This is the official repository for the paper **"Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models"** .
### Feixiang Liu Xiaohui Li, Wenhui Gao, Jiaqing Xiong, Guanchong Niu and Chung Shue Chen*

#### Xidian University，China

### Method Overview

Our approach fuses multimodal data using a Temporally Aware Cross-Attention (TACA) module, conditioned by a Mamba (SSM) based GPS prior.

| Experimental Setup | Proposed Fusion Framework |
| :---: | :---: |
| ![Experimental Setup](photos/fig2.png) | ![TACA Framework](photos/fig5.png) |
| *Figure 2: Data collection platform.* | *Figure 5: The TACA fusion module.* |

### Dataset Scenarios

Experiments are conducted on the DeepSense 6G dataset, covering diverse V2I scenarios.

![Dataset Scenarios](photos/fig6.png)
*Figure 6: Sample single-candidate, multi-candidate, day, and night scenarios.*

---

## Results

### Overall Performance Across Scenarios

Our method ("Ours") consistently outperforms all baselines in Top-k accuracy across eight different real-world scenarios.

![Results Table 1](photos/tab1.png)
*Table II: Performance on Scenarios 1-4.*

![Results Table 2](photos/tab2.png)
*Table III: Performance on Scenarios 5-8.*

### Task-Specific Performance

The model shows state-of-the-art performance when scenarios are grouped into more challenging, specific tasks.

| Single-Target Task | Multi-Target Task |
| :---: | :---: |
| ![Single-Target Task Results](photos/fig7.png) | ![Multi-Target Task Results](photos/fig8.png) |
| *Figure 7: Top-k accuracy (Scenarios 5-8).* | *Figure 8: Top-k accuracy (Scenarios 1-4).* |

| Nighttime Task | Daytime Task |
| :---: | :---: |
| ![Nighttime Task Results](photos/fig10.png) | ![Daytime Task Results](photos/fig11.png) |
| *Figure 10: Top-k accuracy (Scenarios 2, 4, 5).* | *Figure 11: Top-k accuracy (Scenarios 1, 3, 6, 7, 8).* |

### Error Analysis

Confusion matrices show that prediction errors are overwhelmingly concentrated on beams adjacent to the ground truth, indicating high reliability.

![Confusion Matrices](photos/fig12.png)
*Figure 12: Row-normalized confusion matrices for beam prediction across the four tasks.*

---

## Code

Code coming soon.
