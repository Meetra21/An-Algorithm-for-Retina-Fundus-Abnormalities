# Retina Fundus Image Registration (FIRE Dataset)  

This project implements and evaluates **image registration algorithms** on the **Fundus Image Registration (FIRE) dataset**, a benchmark dataset for aligning **retinal fundus images**.  

Image registration is the process of aligning two images with partially overlapping content but acquired from **different viewpoints, devices, or time frames**. In medical imaging, registration is a critical step that enables accurate diagnosis, disease monitoring, and longitudinal analysis.  

---

## 🎯 Project Goal  

- Align **moving images** to **fixed reference images** in the FIRE dataset.  
- Handle challenges such as **scale, rotation, translation, noise, and artifacts**.  
- Explore algorithmic approaches for registration:  
  - Feature-based methods (keypoints, descriptors)  
  - Intensity-based optimization  
  - Deep learning–based deformable registration  
- Evaluate accuracy of registration under different categories of fundus image variations.  

---

## 📂 Dataset: FIRE (Fundus Image Registration Dataset)  

- **Name**: FIRE Dataset  
- **Source**: Papageorgiou Hospital, Aristotle University of Thessaloniki  
- **Size**: 134 image pairs (129 retinal images)  
- **Resolution**: 2912 × 2912 pixels, 45° field of view  
- **Acquisition Device**: Nidek AFC-210 fundus camera  
- **Subjects**: 39 patients  

### Categories  
- **Category A** (14 pairs): Includes retinopathy symptoms (e.g., microaneurysms, vessel tortuosity, cotton-wool spots).  
- **Category B & C**: Varying levels of imaging difficulty due to illumination, artifacts, or acquisition conditions.  

---

## 🧭 Workflow  

### 1. Preprocessing  
- Resize / normalize fundus images  
- Enhance contrast (CLAHE, histogram equalization)  
- Mask background regions  

### 2. Registration Algorithms  
- **Feature-Based**: SIFT, SURF, ORB keypoints → RANSAC-based homography  
- **Intensity-Based**: Mutual Information, Gradient Correlation  
- **Deep Learning Approaches**: CNN/UNet for deformable registration  

### 3. Evaluation  
- Metrics:  
  - Target Registration Error (TRE)  
  - Overlap metrics (IoU, Dice coefficient for vessel maps)  
- Qualitative visualization (before/after alignment)  

---

## 📂 Repository Structure  

- `data/` – FIRE dataset (images and metadata)  
- `preprocessing/` – Scripts for preprocessing and enhancement  
- `registration/` – Algorithms (feature-based, intensity-based, deep learning)  
- `notebooks/` – Jupyter notebooks for experiments  
- `results/` – Registered image outputs and evaluation metrics  

---

## 🚀 How to Run  

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/retina-fundus-registration.git
   cd retina-fundus-registration
