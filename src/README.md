# Synthetic SCG Dataset for Normal, NSTEMI, and STEMI

This repository contains a complete pipeline for generating **synthetic seismocardiogram (SCG) signals**
representing **Normal**, **NSTEMI**, and **STEMI** cardiac conditions.

The dataset is designed for **research and machine learning applications** in cardiac mechanics
and ischemia detection.

---

## What is SCG?

Seismocardiography (SCG) records chest-wall vibrations caused by the mechanical activity of the heart.
Key mechanical events such as **Aortic Valve Opening (AO)** and **post-AO vibrations**
are sensitive to myocardial ischemia.

---

## Dataset Contents

SCG_Datasets/
├── normal_scg_real.npy # Real normal SCG beats
├── normal_scg_gan.npy # GAN-generated normal SCG beats
├── nstemi_scg.npy # Synthetic NSTEMI SCG beats
├── stemi_scg.npy # Synthetic STEMI SCG beats
├── fs.npy # Sampling frequency
└── ao_index.npy # AO sample index



---

## Pipeline Overview

### 1. SCG Preprocessing
- Band-pass filtering (5–40 Hz)
- Z-score normalization
- AO peak detection
- AO-aligned beat segmentation (400 ms before, 600 ms after AO)

### 2. Beat Quality Control
- Beat energy computation
- Removal of noisy and outlier beats

### 3. GAN-Based Normal SCG Generation
- 1D Convolutional GAN trained on clean normal SCG beats
- Produces realistic synthetic normal SCG signals

### 4. NSTEMI SCG Modeling
NSTEMI beats are generated using physiologically motivated modifications:
- AO delay (electromechanical delay)
- AO amplitude reduction (reduced contractility)
- AO peak rounding
- Increased post-AO damping

### 5. STEMI SCG Modeling
STEMI beats simulate severe ischemia using:
- Large AO delay
- Severe AO amplitude collapse
- AO fragmentation
- Strong post-AO vibration damping

---

## Intended Use

- Machine learning model training
- Cardiac ischemia classification (Normal vs NSTEMI vs STEMI)
- Signal processing research
- Biomedical engineering education

---

## Disclaimer

This dataset is **synthetic** and intended **only for research and educational purposes**.
It is **not intended for clinical diagnosis or medical decision-making**.

---

## Author

Developed by **Dinakaran**  
Biomedical Engineer | Medical AI Research

---


