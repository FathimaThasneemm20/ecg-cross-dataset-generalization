# Cross-Dataset Generalisation of Lightweight Deep Learning Models for ECG Arrhythmia Classification

This repository contains the code, experimental configuration, final results, figures, and supplementary materials associated with the study:

**Cross-Dataset Generalisation of Lightweight Deep Learning Models for ECG Arrhythmia Classification**

## Overview

This study evaluates the cross-dataset generalisation of lightweight deep-learning models for three-class ECG arrhythmia classification under a strict zero-shot evaluation protocol.

The models are trained using the MIT-BIH Arrhythmia Database and evaluated on:

- MIT-BIH DS2 for internal evaluation
- St. Petersburg INCART Database for external zero-shot evaluation

The target INCART dataset is excluded from training, fine-tuning, hyperparameter selection, checkpoint selection, and model selection.

## Models

Two lightweight one-dimensional neural-network models are evaluated:

- RR-CNN — 9,353 trainable parameters
- RR-ResNet — 28,121 trainable parameters

Both models use a 256-sample ECG morphology representation together with normalised pre-RR and post-RR interval features.

## Experimental Protocol

- MIT-BIH DS1: source-domain training
- MIT-BIH DS2: held-out internal evaluation
- INCART: unseen external target dataset
- Classification: N/S/V
- Random seeds: 42, 123, 456, 789, 1011
- Primary metric: Macro-F1
- Secondary metric: Accuracy

No target-domain training or adaptation is performed.

## Final Results

### MIT-BIH DS2

| Model | Accuracy | Macro-F1 |
|---|---:|---:|
| RR-CNN | 0.778 ± 0.078 | 0.536 ± 0.032 |
| RR-ResNet | 0.765 ± 0.073 | 0.546 ± 0.053 |

### INCART

| Model | Accuracy | Macro-F1 |
|---|---:|---:|
| RR-CNN | 0.721 ± 0.077 | 0.498 ± 0.024 |
| RR-ResNet | 0.734 ± 0.059 | 0.511 ± 0.035 |

## Repository Contents

```text
figures/
    Final figures and confusion matrices

notebooks/
    Experimental notebook(s)

results/
    Final confusion-matrix results

requirements.txt
    Python package dependencies

CITATION.cff
    Citation metadata

LICENSE
    MIT License
