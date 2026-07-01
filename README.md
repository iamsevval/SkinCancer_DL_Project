# 🧠 DermAI – Dermoscopic Skin Lesion Classification

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red.svg)
![Status](https://img.shields.io/badge/Status-Final%20Project-success)

> **DermAI** is a **Deep Learning** project aimed at automatically classifying skin lesions from dermoscopic skin images.  
The project was developed using **Transfer Learning** and **Fine-Tuning** techniques on the **HAM10000** dataset.

---

## 📌 Project Summary

In this project, the following **7 different skin lesion types** were classified using dermoscopic images:

| Abbreviation | Description |
|--------|---------|
| **MEL** | Melanoma |
| **NV** | Melanocytic nevus |
| **BCC** | Basal cell carcinoma |
| **AKIEC** | Actinic keratosis / intraepithelial carcinoma |
| **BKL** | Benign keratosis |
| **DF** | Dermatofibroma |
| **VASC** | Vascular lesions |

🎯 **Goal:**  
To develop a high-performance deep learning model that supports early diagnosis of skin cancer and is sensitive to class imbalance.

---

## 📊 Dataset

- **Dataset:** HAM10000  
- **Total Images:** 10,015  
- **Source:** [Kaggle – HAM10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000/data)  
- **Characteristics:**  
  - RGB dermoscopic images  
  - Significant class imbalance  
  - Train / validation / test split using stratified split  

---

## 🏗️ Models Used

Different deep learning architectures were compared in the project:

### 🔹 Transfer Learning Models
- **ResNet18 / 34 / 50 / 101**
- **EfficientNet-B0 / B1 / B3**
- **DenseNet-121**
- **Xception**

### 🔹 Techniques Used
- Transfer Learning & Fine-Tuning  
- Weighted CrossEntropy Loss  
- Data Augmentation (Flip, Rotation, ColorJitter)  
- Early Stopping  
- ReduceLROnPlateau Scheduler  

---

## 🏆 Model Performances (Summary)

| Model (Developer) | Architecture | Balanced Accuracy | F1-Score (Macro) | Precision (Macro) | Recall (Macro) | ROC-AUC (Macro-OVR) |
|---------------------|---------|-------------------|------------------|-------------------|----------------|---------------------|
| Model 1 (Şevval Arslan) | Efficient-B0 | 0.82 | 0.78 | 0.75 | 0.82 | **0.97** |
| Model 1 (Şevval Arslan) | ResNet50 | 0.84 | **0.81** | 0.79 | 0.85 | **0.97** |
| Model2 (Zeynep Ekinci) | ResNet18 | 0.83 | 0.68 | 0.83 | **0.83** | 0.96 |
| Model2 (Zeynep Ekinci) | Xception | 0.81 | 0.60 | 0.80 | 0.81 | 0.94 |
| Model3 (Zeynep Şafak) | ResNet-34 | 0.84 | 0.72 | 0.77 | 0.69 | 0.96 |
| **Model3 (Zeynep Şafak)** | **EfficientNet-B3** | **0.90** | **0.81** | **0.84** | 0.78 | **0.97** |
| Model4 (Eda Erol) | EfficientNet-B1 | 0.86 | 0.76 | 0.78 | 0.74 | 0.96 |
| Model4 (Eda Erol) | DenseNet-121 | 0.80 | 0.77 | 0.74 | **0.83** | 0.95 |
| Model5 (Eylül) | ResNet101 | 0.70 | 0.11 | 0.10 | 0.14 | 0.9056 |
| Model5 (Eylül) | EfficentB0 | 0.73 | 0.11 | 0.10 | 0.14 | 0.9080 |

---

## 📌 Overall Evaluation

### 🥇 Best Performing Model: **EfficientNet-B3**
- Highest **Balanced Accuracy**: **0.90**
- Highest **Precision (Macro)**: **0.84**
- High **F1-Score** and **ROC-AUC** values
- More stable performance against class imbalance

### 📊 Other Notable Models
- **ResNet50** → strong Recall and high ROC-AUC performance
- **EfficientNet-B1** → balanced and stable results
- **DenseNet-121** → high Recall value, but lower overall balance

### ⚠️ Low-Performing Models
- Models trained under Model5:
  - low F1-score
  - low precision
  - showed insufficient performance in class separation.
    
---

## 🧰 Tech Stack

Libraries and infrastructure used in the project:

<p align="left">
  <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Torchvision-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="Torchvision" />
  <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" />
  <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Google_Colab-%23F9AB00.svg?style=for-the-badge&logo=google-colab&logoColor=white" alt="Google Colab" />
</p>

* **Modeling:** PyTorch, Torchvision
* **Data Processing:** Pandas, NumPy, Scikit-learn (Stratified Split)
* **Visualization:** Matplotlib, Seaborn
* **Hardware:** Google Colab (with NVIDIA GPU support)

---

## 👩‍💻 Team – DermAI

Our team members and their model responsibilities:

| Member | 🏗️ Models Responsible For |
| :--- | :--- |
| **Şevval Arslan** | `ResNet50`, `EfficientNet-B0` |
| **Zeynep Ekinci** | `ResNet18`, `Xception` |
| **Zeynep Şafak** | `ResNet34`, `EfficientNet-B3` |
| **Miyase Eda Erol** | `EfficientNet-B1`, `DenseNet-121` |
| **Eylül Erdemci** | `EfficientNet-B0`, `ResNet101` |

---

## 🎥 Project Video

> 📢 https://youtu.be/USt4oaalS6s?si=8RL8GzF9-oED-CTr
>

## ⚙️ Installation

```bash
git clone https://github.com/iamsevval/SkinCancer_DL_Project.git
cd SkinCancer_DL_Project
pip install -r requirements.txt
```
