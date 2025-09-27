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
   git clone https://github.com/your-username/brain-mri-segmentation-classification.git
   cd brain-mri-segmentation-classification
