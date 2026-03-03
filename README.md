# PRISM Training & Evaluation Code

This repository contains the training scripts and evaluation notebooks for reproducing the experiments in "Language as a Wave Phenomenon."

## WMT14 (Machine Translation)

| Notebook | Description |
|----------|-------------|
| AIAYN_Baseline_Training.ipynb | Standard Transformer baseline (RoPE) |
| FNet_Train_Last.ipynb | FNet hybrid encoder training |
| Gated_PRISM_train_hybrid_RoPE.ipynb | PRISM model used for mechanistic interpretability analysis |

## WikiText-103 (Masked Language Modeling)

| Notebook | Description |
|----------|-------------|
| WT103_Transformer_Baseline.ipynb | Transformer baseline |
| FNet_Hybrid_Wikitext_Training.ipynb | FNet hybrid (6 spectral + 1 attention) |
| PRISM_wikitext_103_last.ipynb | PRISM with Dynamic RoSE |
| HSSM_Wikitext_Training.ipynb | Hybrid Spectral Sequence Model (FNet rate + PRISM phase streams) |
| WPT_Wikitext_103_Training.ipynb | Wave-Particle Transformer (Transformer sensory + PRISM relational) |

## Evaluation & Analysis

| Notebook | Description |
|----------|-------------|
| Eval_T4_Last.ipynb | Replicates WikiText-103 results using pretrained checkpoints |
| Physical_Validation.ipynb | Generates Figure 3b (iso-energetic validation on WMT14 PRISM) |
| Inspect_Resonances_Last.ipynb | Semantic Phase Compass analysis (Figure 4, Table 2, Appendix figures) |
| Skewness_paper_last.ipynb | Layer-wise skewness and carrier wave threshold analysis (Section 5.4, Figure 5, Table 3) |

## Data

All notebooks pull pre-tokenized data from prism-lab/wikitext-103-prism-32k-seq4k and prism-lab/wmt14-de-en-* on HuggingFace.

## Note on Weight Tying
We utilized LLMs to assist with writing the code for this project. However, the architectural design, physics-based logic, and critical implementation details (such as enforcing FP32 for FFT stability) were strictly human-directed. The authors assume full responsibility for the code.

All models use tied embeddings and uploaded to https://huggingface.co/prism-lab (input embeddings = output projection weights). Checkpoint files contain duplicated weights for compatibility. Evaluation scripts redefine model classes with proper weight tying before loading.

Citation
```bibtex
@article{yildirim2026prism,
  title={Language as a Wave Phenomenon: Semantic Phase Locking and Interference in Neural Networks},
  author={Yıldırım, Alper and Yücedağ, İbrahim},
  journal={arXiv preprint arXiv:2512.01208},
  year={2026},
  url={https://arxiv.org/abs/2512.01208}
}
