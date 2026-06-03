---
title: "EPDBench—An Extended Benchmark and Evaluation Framework for Computational Protein Design Methods"
collection: publications
category: projects
permalink: /research-and-publications/2026-EPDBench
excerpt: '[EPDBench](https://github.com/Zhangke123jimu/EPDBench) is an extended benchmark and evaluation framework built on top of PDBench for fixed-backbone protein sequence design.'
date: 2026-01-01
venue: 'Research project'
paperurl: 'https://github.com/Zhangke123jimu/EPDBench'
---
EPDBench is an extended benchmark and evaluation framework built on top of PDBench for fixed-backbone protein sequence design. Compared with the original PDBench, EPDBench adds a lightweight reference baseline, expands evaluation outputs, 
improves handling of uncommon amino acids, and updates selected dependencies and code paths for better compatibility with current environments. 

Main extensions include:

1. A LightWeightReference (LWR) model has been added as a lightweight, easy-to-maintain baseline rather than a state-of-the-art method.
Why this matters: when a newly added model performs unexpectedly, it can be difficult to tell whether the issue comes from model quality, dataset selection, output formatting, benchmark compatibility, or the benchmark integration itself. LWR provides a fast sanity-check baseline implemented within the same benchmark workflow and is intended to behave stably in this evaluation setting.

2. Perplexity has been added as an evaluation metric, and overall metrics are now reported at the top of the comparison summary.
Why this matters: perplexity is widely used to measure how well a model concentrates probability mass on the true amino acid. Reporting overall metrics first also gives users a clearer high-level view before the original subgroup analyses by architecture and secondary structure.

3. The handling of uncommon amino acids has been expanded to cover more input conditions.
Why this matters: in the original version, ignore_uncommon=True effectively assumed that uncommon residues had already been removed from model outputs. In EPDBench, uncommon residues can now be trimmed automatically when needed so that true labels and model predictions remain aligned under more scenarios.

4. Core requirements and selected code paths have been updated to improve compatibility with current environments.
Why this matters: the original PDBench was released several years ago, and some dependencies and implementation details no longer work reliably in modern setups. EPDBench updates these parts where necessary to keep the benchmark usable.

See [EPDBench](https://github.com/Zhangke123jimu/EPDBench) for detail.
