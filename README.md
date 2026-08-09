# CLP-DD: Closed-Form Linear-Probe Dataset Distillation for Pre-trained Vision Models

[![arXiv](https://img.shields.io/badge/arXiv-2605.07194-b31b1b.svg)](https://arxiv.org/abs/2605.07194)

A closed-form dataset distillation framework for the frozen-backbone linear-probing setting that solves the inner linear probe exactly with a sample-space kernel ridge solver and optimizes synthetic images through a discriminative outer objective, without NTK approximations or inner-loop trajectories.

- Code will be released soon!
- May 2026: Preprint was released.

## 🎯 Key Contributions

- **Closed-Form Bilevel Formulation for Linear Probing**
  Introduces CLP-DD, a dataset distillation framework tailored to modern visual transfer learning, where a frozen pre-trained encoder is followed by lightweight linear probing. Unlike trajectory-based gradient matching or NTK-style closed-form methods designed for from-scratch training, CLP-DD exploits the fact that frozen-feature linear probing admits an exact closed-form solution determined directly by the pre-trained features, with no infinite-width approximation and no inner-loop trajectory.

- **Sample-Space Kernel Ridge Solver**
  Computes the linear probe induced by the synthetic set in closed form via a sample-space kernel ridge solver, keeping the inner problem exact and efficient even when the feature dimension is large.

- **Discriminative Outer Objective with Learned Class Anchors**
  Updates the synthetic images by evaluating the induced classifier on real features through a temperature-scaled softmax cross-entropy, where the classifier columns act as learned class anchors in feature space.

- **The Outer Objective is Decisive**
  Shows that pairing the closed-form inner solver with a standard MSE outer loss substantially underperforms trajectory-based methods, while the discriminative outer loss closes most of the gap, identifying the outer objective as the key design choice in closed-form distillation.

- **Strong Results across Pre-trained Backbones**
  On ImageNet-100 with four pre-trained backbones, CLP-DD substantially improves over LGM without DSA and approaches LGM with DSA, while avoiding costly inner-loop unrolling.

## Citing CLP-DD

If you find this project useful for your research, please use the following BibTeX entry.

```
@article{peng2026clpdd,
  title={Closed-Form Linear-Probe Dataset Distillation for Pre-trained Vision Models},
  author={Peng, Bincheng and Li, Guang and Liu, Ping and Ogawa, Takahiro and Haseyama, Miki},
  journal={arXiv preprint arXiv:2605.07194},
  year={2026}
}
```
