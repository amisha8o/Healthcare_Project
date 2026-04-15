# Healthcare_Project
# 🏥 Diabetic Retinopathy Detection & Severity Classification

## 📌 Project Overview
This project presents an **AI-powered medical imaging system** for automatic detection and grading of Diabetic Retinopathy (DR) from retinal fundus images.

It uses **deep learning (CNN + Transformer hybrid models)** along with advanced training strategies like:
- Class imbalance handling  
- Attention-based learning  
- Ordinal regression  
- Data augmentation techniques  

🎯 **Objective:**  
To build a robust and accurate system for early detection of Diabetic Retinopathy and reduce risk of blindness through automated screening.

---

## 🚨 Problem Statement
Diabetic Retinopathy is a serious eye disease caused by diabetes and can lead to blindness if not detected early. Manual diagnosis is time-consuming and requires experts.

👉 This project automates the process using AI.

---

## 🧠 Key Features

- 🔥 Hybrid CNN Models (EfficientNet + ResNet)
- 🔍 Transformer-based architecture (Swin Transformer)
- 🧩 Lesion-aware attention (MIL framework)
- ⚖ Class imbalance handling (SMOTE, Weighted Loss)
- 🔄 Mixup data augmentation
- ⚙ Hyperparameter tuning using Optuna
- 📊 Performance evaluation (Accuracy, F1-score, Confusion Matrix)

---

## 🧬 Dataset

- 📂 Dataset: APTOS 2019 Blindness Detection
- 🔢 Total Images: 3,296

| Grade | Severity | Description |
|------|----------|-------------|
| 0 | No DR | No disease |
| 1 | Mild | Microaneurysms |
| 2 | Moderate | Hemorrhages |
| 3 | Severe | Vessel damage |
| 4 | Proliferative | Advanced stage |

---

## 🏗 System Architecture

### 1️⃣ Feature Extraction
- EfficientNet (local texture features)
- ResNet (deep feature representation)

### 2️⃣ Feature Fusion
- Concatenation of CNN + Transformer outputs
- Attention-based weighting

### 3️⃣ Classification Head
- Fully connected layers
- Softmax output for 5-class prediction

---

## 🧪 Techniques Used

| Technique | Purpose |
|----------|--------|
| Weighted Sampling | Handle class imbalance |
| Weighted Cross Entropy | Improve minority class learning |
| SMOTE | Synthetic data generation |
| Mixup | Reduce overfitting |
| Optuna | Hyperparameter optimization |
| CORN Loss | Ordinal classification |

---

## 📊 Results Summary

| Model | Technique | Accuracy |
|------|----------|----------|
| Baseline CNN | Simple training | 81% |
| + Class Balancing | Weighted sampling | 82.24% |
| + Loss Tuning | Weighted CE | 83.06% |
| + SMOTE + Mixup | Augmentation | 84% |
| Best Model | Mixup (α=1.0) | 🚀 **86%** |
| Transformer Hybrid | Swin + CNN | 82% |
| Optuna Tuned | Bayesian search | 84.4% |
| MIL + CORN | Ordinal learning | Best loss: 0.2293 |

---

## 📈 Evaluation Metrics

- Accuracy  
- Precision  
- Recall  
- F1 Score  
- Confusion Matrix  

---

## ⚙️ Tech Stack

- Python 🐍  
- PyTorch 🔥  
- NumPy, Pandas  
- OpenCV  
- Albumentations  
- Optuna  
- Matplotlib, Seaborn  

---

## 🔧 Installation

### 1️⃣ Clone Repository
```bash
git clone https://github.com/amisha8o/AMISHA-14.git
cd AMISHA-14

2️⃣ Create Virtual Environment
python -m venv venv
Activate:

Windows
venv\Scripts\activate
Mac/Linux
source venv/bin/activate

3️⃣ Install Dependencies
pip install -r requirements.txt

▶️ How to Run
Train Model:
python train.py

Evaluate Model:
python evaluate.py

Predict on Image:
python predict.py --image path/to/image.jpg

📁 Project Structure
AMISHA-14/
│
├── data/
├── models/
├── utils/
├── notebooks/
│
├── train.py
├── evaluate.py
├── predict.py
├── requirements.txt
└── README.md



