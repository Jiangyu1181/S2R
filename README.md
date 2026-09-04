# S2R: Illumination-Aware Synthetic-to-Real Adaptation for Single-Image Human Material Estimation

**ACM Multimedia 2026 (MM '26)**

Yu Jiang<sup>1</sup>, Jiahao Xia<sup>2</sup>, Jianchi Sun<sup>1</sup>, Jiongming Qin<sup>1</sup>, Tuo Cao<sup>3</sup>, Yusen Wang<sup>4</sup>, Chunxia Xiao<sup>1</sup>

<sup>1</sup> School of Computer Science, Wuhan University  
<sup>2</sup> Faculty of Engineering and IT, University of Technology Sydney  
<sup>3</sup> Institute of AI for Industries, Chinese Academy of Sciences  
<sup>4</sup> DFRD Institute

**Corresponding author:** [Chunxia Xiao](mailto:cxxiao@whu.edu.cn)

[Project Page](https://jiangyu1181.github.io/S2R/) | [Supplementary Material](https://jiangyu1181.github.io/S2R/assets/S2R-Supplementary.pdf)

**Paper DOI:** [10.1145/3767308.3835903](https://doi.org/10.1145/3767308.3835903). The DOI is listed in the camera-ready paper. Its landing page is not yet available.

## Code Release

This is the official repository for S2R. The code is being prepared and will be released here. This repository currently contains the paper information only.

## Overview

S2R estimates human physically based rendering (PBR) attributes from a single image for relighting under novel illumination. Its outputs include surface normals, diffuse albedo, roughness, specular albedo, and subsurface scattering maps.

Models trained on synthetic data can retain shading and highlights in their material predictions on real images. S2R addresses this problem through a two-stage framework. It first learns material estimation from synthetic data with full supervision. It then adapts selected model components to real images using self-supervised reconstruction and teacher-student regularization.

Illumination-aware feature injection helps separate material properties from shading. Physics-inspired fusion combines decoder predictions with external normal and albedo priors. Experiments on synthetic and real-image benchmarks show reduced residual illumination in material estimates and more realistic relighting.

![S2R estimates surface normals, diffuse albedo, roughness, specular albedo, and subsurface scattering from a single human image for relighting.](https://jiangyu1181.github.io/S2R/assets/teaser.jpg)

## Contributions

- Propose a synthetic-to-real adaptation framework for single-image human material estimation to reduce the gap between synthetic and real data.
- Introduce illumination-aware feature injection to incorporate lighting information into latent features and reduce shading residuals in estimated materials.
- Develop selective fine-tuning with teacher-student regularization to improve material estimation on real images while preserving knowledge learned from synthetic supervision.

## Method

1. **Synthetic pretraining.** Train with material supervision and multiple constraints. Illumination-Aware Feature Injection (IAFI) introduces lighting cues into latent features. Physics-inspired Fusion (PIF) refines predictions using external priors.
2. **Real-image adaptation.** Selectively fine-tune components responsible for illumination interpretation and material refinement. Self-supervised reconstruction and teacher-student regularization guide adaptation.

![Overview of S2R, including illumination-aware feature injection, material decoding, and physics-inspired fusion.](https://jiangyu1181.github.io/S2R/assets/method.jpg)

Additional qualitative results are available on the [project page](https://jiangyu1181.github.io/S2R/#results).

## Citation

If you find this work useful, please cite our paper. The following entry is based on the camera-ready metadata.

```bibtex
@inproceedings{jiang2026s2r,
  title = {{S2R}: Illumination-Aware Synthetic-to-Real Adaptation for Single-Image Human Material Estimation},
  author = {Jiang, Yu and Xia, Jiahao and Sun, Jianchi and Qin, Jiongming and Cao, Tuo and Wang, Yusen and Xiao, Chunxia},
  booktitle = {Proceedings of the 34th ACM International Conference on Multimedia},
  year = {2026},
  doi = {10.1145/3767308.3835903},
  url = {https://doi.org/10.1145/3767308.3835903}
}
```
