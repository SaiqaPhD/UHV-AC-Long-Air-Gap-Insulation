from pathlib import Path

readme = """# UHV AC Long Air Gap Insulation

## Overview

This repository contains the research and data-analysis work carried out during my MSc thesis on **UHV AC insulation and breakdown characteristics in long rod–plane air gaps**.

The experimental work was conducted at the **State Grid Corporation of China UHV AC Test Base, Wuhan, China**. The study focused on analyzing high-speed breakdown/streamer–leader images and experimental measurements obtained from long air-gap discharge experiments.

## Research Work

As an MSc student, I was responsible for the research workflow, including:

- Processing and analyzing raw experimental data.
- Preprocessing high-speed breakdown images.
- Extracting relevant discharge/arc features from experimental images.
- Developing machine-learning pipelines for experimental-data analysis.
- Estimating discharge characteristics from image and experimental data.
- Evaluating model performance using statistical error and regression metrics.
- Interpreting the experimental and machine-learning results.

## Experimental Setup

The main experimental configuration consisted of a **10 m rod–plane air gap** under high-voltage impulse excitation. The experiments were performed using a high-voltage impulse system at the State Grid UHV AC Test Base in Wuhan, China.

## Data Processing

The image-processing workflow included operations such as:

1. Raw high-speed image acquisition
2. Grayscale conversion
3. Noise reduction / filtering
4. Background subtraction
5. Image normalization
6. Image transformation and augmentation
7. Feature extraction / preparation for machine-learning models

## Machine Learning

Machine-learning and deep-learning methods were developed to analyze the experimental data and estimate discharge-related parameters. The pipelines were trained and evaluated using experimentally obtained datasets.

## Publications

The research resulted in international conference publications, including work presented/published through IEEE conferences.

### Related Publications

- **Experimental Data Analysis of Positive Streamer-Leader Dynamics in Long Air Gaps Under Slow Front Impulse Voltages Using Machine Learning**
- **Deep Learning-Based Estimation of Arc Length from High-Speed Breakdown Images in 10 m Rod-Plane Air Gap**

## Repository Structure

```text
UHV-AC-Long-Air-Gap-Insulation/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│
├── src/
│   ├── preprocessing/
│   ├── machine_learning/
│   └── analysis/
│
├── models/
│
├── figures/
│
├── results/
│
├── thesis/
│
├── publications/
│
└── README.md
