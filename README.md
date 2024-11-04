# ABIDE-FMRI-Augmentation-ViT-ASD


This repository focuses on leveraging data augmentation and Vision Transformer (ViT) architectures to classify Autism Spectrum Disorder (ASD) using fMRI data from the ABIDE (Autism Brain Imaging Data Exchange) dataset. The main goal is to apply modern transformer-based models and data augmentation techniques to enhance ASD classification performance.

---

## Overview

The project involves:
- **Data Source**: Functional MRI (fMRI) data from the ABIDE dataset.
- **Data Augmentation**: Techniques to enhance training by generating synthetic fMRI data (In progress).
- **Model Architecture**: Vision Transformer (ViT) applied to 4D fMRI data, treated as sequences of flattened patches.
- **Goal**: Classify ASD vs. control using the fMRI data.

---

## Dataset

The dataset used is the publicly available **ABIDE dataset**, which includes fMRI data for individuals with Autism Spectrum Disorder (ASD) and healthy controls.

- **fMRI data format**: `.nii.gz` files, representing 4D fMRI data.
- **Phenotypic data**: Includes metadata like diagnosis (DX), age, and other clinical information.

---

## Project Structure

- `Fmri_Data/`: Directory containing the original `.nii.gz` fMRI files for each subject.
- `Extracted_Fmri_Data/`: Directory where processed and fla
