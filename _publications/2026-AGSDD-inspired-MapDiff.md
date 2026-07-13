---
title: "Investigating the Effect and Mechanism of Semantic Alignment in Fixed-Backbone Protein Sequence Design"
collection: publications
category: aidd_projects
permalink: /research-and-publications/2026-AGSDD-inspired-MapDiff
excerpt: 'This study examines the transferability of AGSDD-inspired semantic alignment (SA) to MapDiff as a case study and further explores its mechanism related to output probability distribution.'
date: 2026-05-01
venue: 'Research project'
paperurl: 'https://www.researchsquare.com/article/rs-10307155/v1'
---
AGSDD proposed semantic alignment (SA) as a way to incorporate amino-acid-level semantic information into diffusion-based inverse folding, based on the idea that amino-acid types are not merely discrete class indices but may also encode biochemical, functional, and evolutionary regularities. However, it remains unclear whether this idea can be transferred beyond the original AGSDD framework, and the output-level effect of SA remains underexplored. In this study, we use MapDiff as a case study to examine the transferability of AGSDD-inspired SA and analyze its effect on the final amino-acid probability distribution. AGSDD-inspired SA can be integrated into MapDiff and modestly improves perplexity while leaving median recovery largely unchanged. The AGSDD-style increase in true-amino-acid semantic attention is reproducible, but output-level analyses suggest that SA mainly behaves as a distributional regularizer or smoother. Current NSSR and BLOSUM-based probability-mass analyses do not provide clear evidence that SA enhances BLOSUM-defined biochemical similarity.

![AGSDD-inspired-MapDiff](https://raw.githubusercontent.com/Zhangke123jimu/AGSDD-inspired-MapDiff/main/image/AGSDD-inspired-MapDiff.svg)

See [AGSDD-inspired-MapDiff](https://github.com/Zhangke123jimu/AGSDD-inspired-MapDiff) for details.
