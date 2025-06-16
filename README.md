# Detection of Diabetic Retinopathy

**Author:** Vishvas Ranjan, UM DAE Centre for Excellence in Basic Sciences, Mumbai  
**Competition:** Inter-INCI Entrepreneurial Summit (IIE‑S) 2025 (IISER • NISER • CEBS • IISc) @ IISER Kolkata  
**Result:** 2nd Runner‑Up among teams of PhD students, with my team composed of master’s‑level students  

---

## 🚀 Project Vision

This was an ideathon‑style challenge: build a proof‑of‑concept using only our existing skills to see if a “from‑scratch” approach could yield promising results.  
> **Note:** Code quality and optimization are ongoing :— our current goal is to demonstrate that the idea works; domain experts can later refine and extend it.

---

## 📋 Overview

We tackled diabetic retinopathy (DR) classification using clinician‑labeled retinal images. Key steps:

1. **Dataset & Objective**  
   - **Source:** Kaggle Diabetic Retinopathy Classification competition  
     (5‑level labels by clinicians)  
     https://www.kaggle.com/competitions/diabetic-retinopathy-classification-f1-score-4/data  
   - **Sample:** 2,200 images  
   - **Goal:** Train deep CNNs, measure performance via F1‑Score & accuracy, and handle class imbalance.

2. **Model Experiments (5‑Class)**  
   - Architectures: ResNet50, EfficientNetB4, DenseNet121  
   - Loss & Metrics: Focal Loss; track both accuracy and F1‑Score  
   - Class imbalance: Level 0 = 52% → model easily fits majority but struggles on minority  
   - **Validation Accuracies:**  
     - ResNet50: 73%  
     - EfficientNetB4: 69%  
     - DenseNet121: 77%  
   - **After tuning (augments, class‑weights): F1‑Scores on validation**  
     - ResNet50: 92  
     - EfficientNetB4: 77  
     - DenseNet121: 94  

3. **Binary Classification Approach**  
   - Merge labels: Level 0 → Class 0; Levels 1–4 → Class 1 (balanced classes)  
   - Model: DenseNet121  
   - **Results:**  
     - Training Acc.: 92% | Validation Acc.: 90%  
     - F1‑Scores: > 90 (both train & val)  
   - **Loss Curves:**  
     - Training loss ↓ 0.20 → 0.00 over 25 epochs  
     - Validation loss ↓ 0.15 → 0.05, closely tracking training → minimal overfitting  

---

## 🎯 Key Insights

- **DenseNet121** delivered the best balance of accuracy & F1, with smooth, stable training curves.  
- **F1‑Score** is the critical metric for imbalanced medical data—here it uncovers true performance beyond raw accuracy.  
- **Binary task** (healthy vs. DR) resolves extreme imbalance and yields robust, high‑confidence results.  
- This work is **proof‑of‑concept**—we invite ML experts to build on our pipeline.

---

## 📊 Slide‑Ready Summary

- **Dataset & Objective:**  
  - 2,200 clinician‑labeled DR images (5 levels) from Kaggle  
  - Focus: F1‑Score & accuracy; address class imbalance  

- **5‑Class Experiments:**  
  - Models: ResNet50, EfficientNetB4, DenseNet121  
  - Validation Accuracies: 73% | 69% | 77%  
  - Tuned F1‑Scores: 92 | 77 | 93 → DenseNet121 shines  

- **Preprocessing & Training:**  
  - 80/20 train/val split; Albumentations for augments  
  - Focal Loss + class weights  
  - Spiky training curves → need robust augments  

- **Binary Classification:**  
  - Level 0 vs. Levels 1–4 → balanced two‑class task  
  - DenseNet121 → 92% train, 90% val acc; F1 > 90  

- **Loss Evolution:**  
  - Training loss: 0.20 → 0.00  
  - Validation loss: 0.15 → 0.05 (stable convergence)  

- **Conclusion:**  
  - Provides intuition, not a final model  
  - Encourages experts to iterate  
  - Highlights F1‑Score’s importance in imbalanced medical datasets  

---

## 🔗 Dataset

- **Kaggle Diabetic Retinopathy Classification**  
  https://www.kaggle.com/competitions/diabetic-retinopathy-classification-f1-score-4/data

---

## 📖 Next Steps

- Code cleanup & modularization  
- Hyperparameter sweeps & advanced augmentations  
- Integration of expert‑built architectures and pipelines  

---

*Thanks for checking out our proof‑of‑concept! We hope it sparks new ideas in DR detection.*  
