# PRISM: Pay Attention Later
**Official Implementation for arXiv:2512.01208**

This repository contains the experimental code for **PRISM** (Phase-Resonant Intelligent Spectral Model) and the **ISMR** (Iterative Semantic Map Refinement) diagnostic protocol.

All notebooks were created and executed using Google Colab.

## 📂 1. The Marathon (General Training)
*Training the models from scratch on WMT14/Multi30k to measure general competence.*
* **`PRISM_train.ipynb`** - Main training script for the PRISM architecture ($O(N \log N)$ Harmonic Convolutions).
* **`AIAYN_Baseline_Training.ipynb`** - Training script for the Standard Transformer Baseline ("Attention Is All You Need").
* **`Train_With_Helsinki_Pretrained_Embeddings.ipynb`** - Control experiment using external pre-trained embeddings to verify initialization gains.

## 📂 2. The Sprint (Few-Shot Plasticity)
*Fine-tuning pre-trained models on 5 novel concepts (e.g., "Schmerzhotel") to test plasticity vs. forgetting.*
* **`PRISM_few_shot_experiment.ipynb`** - PRISM "Sprint" protocol (High acquisition, negligible forgetting).
* **`Baseline_few_shot_experiment_py.ipynb`** - Transformer Baseline "Sprint" protocol (Demonstrates catastrophic forgetting).

## 📂 3. ISMR Diagnostic (The "Tax")
*The "Iterative Semantic Map Refinement" protocol used to diagnose the Semantic Alignment Tax.*
* **`Iterative_trainer_v2.ipynb`** - (Latest) Implementation of the ISMR pipeline (Train Iter 1 $\to$ Extract Map $\to$ Train Iter 2).
* **`Iterative_Trainer.ipynb`** - (Legacy) Earlier version of the ISMR trainer.
* **`ISMR_test_results.ipynb`** - Visualization and analysis of the learning curves (e.g., the "20-layer vs 1-layer" comparison).
* **`Ablation_Study_v2.ipynb`** - (Latest) Geometric vs. Statistical ablation studies (Shuffled Maps).
* **`Ablation_Study.ipynb`** - (Legacy) Initial ablation experiments.

## 📂 4. Data Processing
* **`Multi30k_data_processing.ipynb`** - Pre-processing scripts for the Multi30k dataset used in the diagnostic phase.
* **`Multi3k_data_processing.ipynb`** - (Legacy) Alternate processing script.

---
**Citation:**
```bibtex
@misc{yildirim2025payattentionlater,
      title={Pay Attention Later: From Vector Space Diffusion to Linearithmic Spectral Phase-Locking}, 
      author={Alper Yıldırım and İbrahim Yücedağ},
      year={2025},
      eprint={2512.01208},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
