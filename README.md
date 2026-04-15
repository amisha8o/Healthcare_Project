# Healthcare_Project
# 🏥 Diabetic Retinopathy Detection & Severity Classification

## 📖 Overview
This project presents a **state-of-the-art deep learning pipeline** for automated detection and grading of Diabetic Retinopathy (DR) using retinal fundus images.

The system integrates:
- Hybrid CNN–Transformer architectures
- Ordinal-aware learning strategies
- Lesion-focused attention mechanisms
- Automated hyperparameter optimization

The goal is to build a **clinically reliable, interpretable, and scalable DR screening system**.

---

## 🚀 Key Features

### 🧠 Hybrid Model Architecture
- Dual-branch feature extraction:
  - CNN (EfficientNet, ResNet) → local features
  - Transformer (Swin Transformer) → global context
- Feature fusion using concatenation + fully connected layers

✅ Achieved up to **86% validation accuracy**

---

### 🧩 Lesion-Aware Attention (MIL)
- Multiple Instance Learning (MIL):
  - Combines global image + lesion patches
- Attention mechanism identifies critical regions
- Integrated CORN loss for ordinal regression

✅ Best Validation Loss: **0.2293**

---

### ⚖ Class Imbalance Handling
- WeightedRandomSampler
- Weighted Cross-Entropy Loss
- SMOTE (oversampling)
- Mixup Augmentation (α = 1.0)

✅ Improved minority class performance and recall

---

### 🔍 CNN–Transformer Fusion
- EfficientNet-B4 + Swin Transformer
- CNN → texture features
- Transformer → spatial dependencies

✅ Better contextual understanding (82% accuracy)

---

### ⚙ Hyperparameter Optimization
- Optuna (Bayesian optimization)
- Tuned:
  - Learning rate
  - Optimizer
  - Dropout
  - Mixup parameter

✅ Best Accuracy: **84.4%**

---

## 🧬 Dataset
- **APTOS 2019 Blindness Detection (Kaggle)**
- Total Images: 3,296

| Label | Severity | Description |
|------|--------|-------------|
| 0 | No DR | No abnormality |
| 1 | Mild | Microaneurysms |
| 2 | Moderate | Hemorrhages |
| 3 | Severe | Vascular damage |
| 4 | Proliferative | Neovascularization |

---

## 🧰 Data Preprocessing & Augmentation

### Preprocessing
- Resize: 224×224 / 384×384
- Normalization: ImageNet mean & std
- CLAHE for contrast enhancement

### Augmentations
- Random rotation (±15°)
- Horizontal flip
- Brightness/contrast adjustment
- Random resized crop
- Mixup augmentation

---

## 🧠 Model Experiments

| Exp | Model | Technique | Result |
|-----|------|----------|--------|
| 1 | Hybrid CNN | Baseline | 81% |
| 2 | + Sampling | Balanced batches | 82.24% |
| 3 | + Weighted Loss | Stability | 83.06% |
| 4 | + SMOTE + Mixup | Regularization | 84% |
| 5 | + Mixup Only | Best model | **86%** |
| 6 | CNN + Transformer | Context learning | 82% |
| 7 | Optuna Tuned | Optimization | 84.4% |
| 8 | MIL + CORN | Ordinal learning | **0.2293 loss** |

---

## 🧪 Training Setup
- Framework: PyTorch  
- GPU: CUDA (Colab/Kaggle)  
- Batch Size: 32 (8 for MIL)  
- Epochs: 20–30  
- Optimizers: Adam, RMSProp, AdamW  

---

## 📊 Evaluation Metrics
- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Confusion Matrix  
- Quadratic Weighted Kappa  

---

## 📈 Results Summary

| Technique | Performance | Observation |
|----------|------------|------------|
| Baseline | 81% | Starting point |
| Mixup | **86%** | Best accuracy |
| SMOTE + Mixup | 84% | Balanced training |
| Optuna | 84.4% | Tuned performance |
| MIL + CORN | 0.2293 loss | Best ordinal learning |

---

## 🔍 Key Insights
- Mixup is the most effective regularization technique
- SMOTE improves minority class recall
- Ordinal loss improves medical grading accuracy
- Transformers add context but require higher computation

---

## 🧠 Interpretability
- Grad-CAM for visual explanations
- Highlights:
  - Microaneurysms
  - Hemorrhages
- Improves clinical trust

---

## 🌐 Deployment
- Backend: Flask / FastAPI  
- Frontend: Streamlit / React  

### Features:
- Upload retinal image
- Predict DR severity
- Visual explanation (heatmaps)

---

## 🔮 Future Work
- Vision Transformer (ViT)
- ConvNeXt backbone
- Multi-dataset training (IDRiD, Messidor)
- Mobile/edge deployment

---

## 🏆 Resume Highlight
**Developed a hybrid CNN–Transformer based Diabetic Retinopathy detection system achieving 86% accuracy with lesion-aware attention and ordinal regression.**

---

## 📚 References
- APTOS 2019 Blindness Detection Dataset (Kaggle)
- Research papers on CNN, Transformer, and medical imaging
- Optuna documentation

---

## 👩‍💻 Author
**Amisha Kumari**
