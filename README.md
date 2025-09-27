# 🧠 Brain MRI Segmentation & Classification Project

This project explores **medical image analysis** using deep learning.  
It focuses on:  
- **Segmentation** of brain tumors from 3D FLAIR MRI scans using a **3D U-Net**.  
- **Classification** using extracted imaging features and clinical data.  

The goal is **learning & experimentation** with medical imaging pipelines, not achieving state-of-the-art results (the dataset is small, so metrics are limited).

---

## 📂 Data

We used the **Brain Mets Lung MRI Path Segs** dataset:  
🔗 [The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/collection/brain-mets-lung-mri-path-segs)

- **MRI scans**: 3D FLAIR sequences (`.nii.gz` files).  
- **Segmentation masks**: Whole-tumor binary masks (`.nii.gz`).  
- **Clinical data**: Patient information (structured tabular data).

⚠️ **Note:** Data is large and not included in this repo. Please download it directly from TCIA.

---

## ⚙️ Setup

1. **Clone the repo**
   ```bash
   git clone https://github.com/ahmedmajid2323/Brain-MRI-Segmentation-Classification.git

2. **Create a virtual environment**
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # Linux / macOS
   .venv\Scripts\activate      # Windows

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt

4. **Data organization**
   ```bash
  data/
   ├── dataset/         
      ├── patient_id/   
  cilinical_data.xlsx

---

  ## 🧩 Pipeline Overview

### 🔹 Segmentation Pipeline
1. **Load data** → 3D FLAIR MRI + corresponding tumor masks.  
2. **Preprocessing**:
   - Align/resample masks  
   - N4 bias field correction (intensity correction)  
   - Normalization  
   - Cropping around brain/tumor  
3. **Split** into training & testing sets.  
4. **Train** a **3D U-Net (PyTorch)**.  
5. **Evaluate** on test set → **Dice score** as main metric.  
6. **Inference**:
   - Preprocess raw MRI  
   - Predict tumor mask  
   - Reinstate mask into full volume  
   - Overlay with FLAIR and **visualize in Napari (3D)**  

---

### 🔹 Classification Pipeline
1. **Clinical data preprocessing**:
   - Remove duplicates  
   - One-hot encoding for categorical variables  
   - Standardization / normalization  
2. **Imaging feature extraction**:
   - Convert MRI slices to **ResNet50 input format** (224×224, 3-channel, ImageNet normalization).  
   - Use **ResNet50 pretrained on ImageNet** to extract **2048-dimensional feature vectors**.  
3. **Combine features**:
   - Clinical features + Imaging features.  
4. **Classification models**:
   - Tested **Random Forest** and **XGBoost**.  
   - Evaluation with **accuracy, precision, recall, F1-score, confusion matrix**.  

---

## 📊 Metrics
- **Segmentation**: Dice score (moderate due to small dataset).  
- **Classification**: Accuracy, precision, recall, F1-score (limited by dataset size).  

⚠️ This project is **research & learning-oriented** → performance is constrained by dataset size.

---

## 🔍 Visualization
- **Napari** → 3D MRI visualization + overlayed predicted masks.  
- **PyVista / Plotly** → Rendering and visual exploration.  
- **Confusion Matrix & Metrics** → Classification analysis.  

     


   
