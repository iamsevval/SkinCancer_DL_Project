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

| Model | Accuracy | Weighted F1 | ROC-AUC |
|------|---------|-------------|---------|
| **EfficientNet-B3** ⭐ | **0.90** | **0.90** | **0.97** |
| ResNet50 | 0.86 | 0.87 | 0.97 |
| EfficientNet-B0 | 0.86 | 0.87 | 0.97 |
| ResNet34 | 0.84 | 0.84 | 0.96 |
| EfficientNet-B1 | 0.86 | 0.86 | 0.96 |

📌 **En iyi model:** **EfficientNet-B3**  
- Sınıf dengesizliğine karşı en dengeli performans  
- Melanom ve pre-kanser sınıflarında yüksek F1-score  
- Klinik açıdan daha güvenilir sonuçlar  

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

