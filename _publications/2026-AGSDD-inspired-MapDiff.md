---
title: "A geometry-corrected, AGSDD-inspired extension of MapDiff"
collection: publications
category: aidd_projects
permalink: /research-and-publications/2026-AGSDD-inspired-MapDiff
excerpt: 'A geometry-corrected, AGSDD-inspired extension of MapDiff for fixed-backbone protein sequence design.'
date: 2026-01-01
venue: 'Research project'
paperurl: 'https://github.com/Zhangke123jimu/AGSDD-inspired-MapDiff'
---
[AGSDD-inspired-MapDiff](https://github.com/Zhangke123jimu/AGSDD-inspired-MapDiff) provides a PyTorch implementation of the AGSDD-inspired-MapDiff. [MapDiff](https://github.com/peizhenbai/MapDiff/) (**Ma**sk-**p**rior-guided denoising **Diff**usion) is a deep diffusion model with mask-prior-guided denoising to improve the inverse protein folding task. 
It works on 3D protein backbone structures to iteratively predict the feasible 1D sequences of amino acids. [AGSDD](https://doi.org/10.1007/978-3-032-06066-2_21) suggests that can improve model performance by aligning hidden representations with amino-acid type semantics. This idea is compatible with MapDiff because both methods rely on message passing and iterative denoising.
Inspired by that, as an exploratory experiment, this repository modifies the MapDiff's architecture to embed semantic module of AGSDD. In addition, the repository 
fixes several issues in the backbone dihedral feature calculation of MapDiff implementation. Together, these changes lead to modest improvements in recovery and perplexity, with additional diagnostic analyses provided in the technical report. 

Below is a summary table: 

|            Version (CATH 4.2)            | Model Parameters | Median Recovery Rate (%) | Perplexity |
|:----------------------------------------:|:----------------:|:------------------------:|:----------:|
| Reported MapDiff result (marginal prior) |      14.7M       |          60.93           |    3.43    |
|          Original reproduction           |      14.7M       |          60.97           |    3.54    |
|             Dihedral-fixed*              |      14.7M       |          61.23           |    3.54    |
|  Semantic-alignment & Dihedral-fixed**   |      16.3M       |          61.41           |    3.41    |

*Dihedral-fixed: See [Technical Report-Appendix]([Technical Report-Appendix](https://github.com/Zhangke123jimu/AGSDD-inspired-MapDiff/blob/main/technical_report.md#appendix)) for details. \
**Semantic-alignment & Dihedral-fixed: See [Technical Report](https://github.com/Zhangke123jimu/AGSDD-inspired-MapDiff/blob/main/technical_report.md) for details.
 

This repository also includes several engineering improvements, including DDP-based distributed training, batch downloading and graph construction, and checkpoint resumption.

Hardware note: The original MapDiff experiments were reported on A100 GPUs. The model is trained in FP32 both in original and this repository, so mixed-precision acceleration is not fully used. To keep the reported results comparable, all main-model training runs were performed on 2 x A100 GPUs. 
For exploratory experiments, rented consumer GPUs with sufficient VRAM may be a practical lower-cost alternative and can be competitive in wall-clock time for FP32 training, although this depends on the specific hardware。

![MapDiff](https://raw.githubusercontent.com/Zhangke123jimu/AGSDD-inspired-MapDiff/main/image/AGSDD-inspired-MapDiff.png)

See [AGSDD-inspired-MapDiff](https://github.com/Zhangke123jimu/AGSDD-inspired-MapDiff) for details.
