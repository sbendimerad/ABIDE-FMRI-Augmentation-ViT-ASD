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

- `fmri_Data/`: Directory containing the original `.nii.gz` fMRI files for each subject.
- `Extracted_fmri_Data/`: Directory where processed and flattened fMRI files are stored.
  - `Training_Data_Pheno.csv`: CSV file for training data, containing file paths and corresponding labels (ASD or control).
  - `Validation_Data_Pheno.csv`: CSV file for validation data, similarly containing file paths and labels.
  - `Total_Data_Pheno.cs`T: Full dataset CSV file containing all subjects used for splitting into train/validation sets.
- `prepare_fmri_dataset.ipynb`: A Juyter notebook to extract and preprocess the data (A first draft, need to be recreate in a .py script with classes)
- `ViT_Benchmark_fMRI.ipynb` : A jupyter notebook to benchmark ViT models (A first draft, need to be recreate in a .py script with classes)

---

## Model

We utilize a **Vision Transformer (ViT)** architecture adapted for fMRI data:

- **Patch Extraction**: fMRI 4D volumes are flattened into 2D sequences by treating the time component as a separate channel.
- **Embedding Layer**: Each patch is projected into an embedding space.
- **Multi-Head Attention**: Self-attention is applied across patches to capture temporal and spatial relationships.
- **Classification Head**: Output is processed through fully connected layers to perform binary classification (ASD or control).

---

## Setup

### Prerequisites

- Python 3.8+
- TensorFlow 2.x
- NumPy
- SciPy
- Pandas
- NiBabel (for handling fMRI `.nii.gz` files)
- Scikit-learn


## To-Do

- [ ] **Implement Data Augmentation**: 
    - Add GAN or other data augmentation techniques to increase the training dataset and improve model generalization.
- [ ] **Test the Simple Vision Transformer (ViT) Model with the Data Augmentation**: 
    - Re run the basic ViT model for fMRI dataset + augmented dataset.
- [ ] **Extend your script to loop over multiple site names**: 
    - The script run actually only on a sample of 100 images to ensure the code is working.
- [ ] **Add More Complex ViT Model with Transfer Learning**: 
    - Introduce a more advanced ViT model leveraging pre-trained weights and transfer learning for better performance.
- [ ] **Parameter Tuning**: 
    - Perform hyperparameter tuning for the Vision Transformer model (e.g., patch size, embedding dimension, number of layers) to optimize the model’s performance.
- [ ] **Add requirements.txt**: 
    - List the Python packages and versions used in the project for easy environment setup.
- [ ] **Optimize and Convert Jupyter Notebooks into Python Classes**: 
    - Refactor the project by converting the Jupyter notebook into Python scripts with a modular class-based design for easier maintenance and scalability.
