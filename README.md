# 🧠 DermAI – Dermatoskopik Cilt Lezyonları Sınıflandırması

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red.svg)
![Status](https://img.shields.io/badge/Status-Final%20Project-success)

> **DermAI**, dermatoskopik cilt görüntülerinden cilt lezyonlarını otomatik olarak sınıflandırmayı amaçlayan bir **Derin Öğrenme (Deep Learning)** projesidir.  
Proje, **HAM10000** veri seti üzerinde **Transfer Learning** ve **Fine-Tuning** teknikleri kullanılarak geliştirilmiştir.

---

## 📌 Proje Özeti

Bu projede, dermatoskopik görüntüler kullanılarak aşağıdaki **7 farklı cilt lezyonu** sınıflandırılmıştır:

| Kısaltma | Açıklama |
|--------|---------|
| **MEL** | Melanom |
| **NV** | Melanositik nevüs |
| **BCC** | Bazal hücreli karsinom |
| **AKIEC** | Aktinik keratoz / intraepidermal karsinom |
| **BKL** | Benign keratoz |
| **DF** | Dermatofibroma |
| **VASC** | Vasküler lezyonlar |

🎯 **Amaç:**  
Cilt kanserinin erken teşhisini destekleyecek, sınıf dengesizliğine duyarlı ve yüksek performanslı bir derin öğrenme modeli geliştirmek.

---

## 📊 Veri Seti

- **Veri Seti:** HAM10000  
- **Toplam Görüntü:** 10.015  
- **Kaynak:** [Kaggle – HAM10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000/data)  
- **Özellikler:**  
  - RGB dermatoskopik görüntüler  
  - Belirgin sınıf dengesizliği  
  - Stratified split ile eğitim / doğrulama / test ayrımı  

---

## 🏗️ Kullanılan Modeller

Projede farklı derin öğrenme mimarileri karşılaştırılmıştır:

### 🔹 Transfer Learning Modelleri
- **ResNet18 / 34 / 50 / 101**
- **EfficientNet-B0 / B1 / B3**
- **DenseNet-121**
- **Xception**

### 🔹 Kullanılan Teknikler
- Transfer Learning & Fine-Tuning  
- Weighted CrossEntropy Loss  
- Data Augmentation (Flip, Rotation, ColorJitter)  
- Early Stopping  
- ReduceLROnPlateau Scheduler  

---

## 🏆 Model Performansları (Özet)

| Model (Geliştirici) | Mimari | Balanced Accuracy | F1-Score (Macro) | Precision (Macro) | Recall (Macro) | ROC-AUC (Macro-OVR) |
|---------------------|---------|-------------------|------------------|-------------------|----------------|---------------------|
| Model 1 (Şevval Arslan) | Efficient-B0 | 0.82 | 0.78 | 0.75 | 0.82 | **0.97** |
| Model 1 (Şevval Arslan) | ResNet50 | 0.84 | **0.81** | 0.79 | 0.85 | **0.97** |
| Model2 (Zeynep Ekinci) | ResNet18 | 0.83 | 0.68 | 0.83 | **0.83** | 0.96 |
| Model2 (Zeynep Ekinci) | Xception | 0.81 | 0.60 | 0.80 | 0.81 | 0.94 |
| Model3 (Zeynep Şafak) | ResNet-34 | 0.84 | 0.72 | 0.77 | 0.69 | 0.96 |
| **Model3 (Zeynep Şafak)** ⭐ | **EfficientNet-B3** | **0.90** | **0.81** | **0.84** | 0.78 | **0.97** |
| Model4 (Eda Erol) | EfficientNet-B1 | 0.86 | 0.76 | 0.78 | 0.74 | 0.96 |
| Model4 (Eda Erol) | DenseNet-121 | 0.80 | 0.77 | 0.74 | **0.83** | 0.95 |
| Model5 (Eylül) | ResNet101 | 0.70 | 0.11 | 0.10 | 0.14 | 0.9056 |
| Model5 (Eylül) | EfficentB0 | 0.73 | 0.11 | 0.10 | 0.14 | 0.9080 |

---

## 📌 Genel Değerlendirme

### 🥇 En Başarılı Model: **EfficientNet-B3**
- En yüksek **Balanced Accuracy**: **0.90**
- En yüksek **Precision (Macro)**: **0.84**
- Yüksek **F1-Score** ve **ROC-AUC** değerleri
- Sınıf dengesizliğine karşı daha stabil performans

### 📊 Dikkat Çeken Diğer Modeller
- **ResNet50** → güçlü Recall ve yüksek ROC-AUC performansı
- **EfficientNet-B1** → dengeli ve stabil sonuçlar
- **DenseNet-121** → Recall değeri yüksek olsa da genel denge daha düşük

### ⚠️ Düşük Performanslı Modeller
- Model5 altında eğitilen modeller:
  - düşük F1-score
  - düşük precision
  - sınıf ayrımında yetersiz performans göstermiştir.

### 🧠 Sonuç
Genel metrikler değerlendirildiğinde **EfficientNet-B3**, hem doğruluk hem de sınıf bazlı denge açısından en güvenilir model olarak öne çıkmaktadır.
---



## 🧰 Teknoloji Yığını (Tech Stack)

Projede kullanılan kütüphaneler ve altyapı:

<p align="left">
  <img src="https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Torchvision-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white" alt="Torchvision" />
  <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" />
  <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Google_Colab-%23F9AB00.svg?style=for-the-badge&logo=google-colab&logoColor=white" alt="Google Colab" />
</p>

* **Modelleme:** PyTorch, Torchvision
* **Veri İşleme:** Pandas, NumPy, Scikit-learn (Stratified Split)
* **Görselleştirme:** Matplotlib, Seaborn
* **Donanım:** Google Colab (NVIDIA GPU desteği ile)

---

## 👩‍💻 Ekip – DermAI

Takım üyelerimiz ve model sorumlulukları:

| Üye | 🏗️ Sorumlu Olduğu Modeller |
| :--- | :--- |
| **Şevval Arslan** | `ResNet50`, `EfficientNet-B0` |
| **Zeynep Ekinci** | `ResNet18`, `Xception` |
| **Zeynep Şafak** | `ResNet34`, `EfficientNet-B3` |
| **Miyase Eda Erol** | `EfficientNet-B1`, `DenseNet-121` |
| **Eylül Erdemci** | `EfficientNet-B0`, `ResNet101` |

---

## 🎥 Proje Videosu

> 📢 https://youtu.be/USt4oaalS6s?si=8RL8GzF9-oED-CTr
>

## ⚙️ Kurulum

```bash
git clone https://github.com/iamsevval/SkinCancer_DL_Project.git
cd SkinCancer_DL_Project
pip install -r requirements.txt

