# Binary and Multi-class Classification of Skin Lesions Using Machine Learning

This project focuses on the **binary and multi-class classification** of skin lesions using traditional **image preprocessing, feature extraction**, and **machine learning techniques**. The aim is to explore the effectiveness of handcrafted features and machine learning classifiers for skin lesion classification and to address data imbalance issues.

---

## **Dataset Details**

### **Binary Dataset**
- **Classes:** Nevus vs. Others
- **Train Images:** 15,195
- **Validation Images:** 3,796
- **Balanced Dataset**

### **Multi-class Dataset**
- **Classes:** 
  - Basal Cell Carcinoma (BCC)
  - Melanoma (Mel)
  - Squamous Cell Carcinoma (SCC)
- **Train Images:** 5,082
- **Validation Images:** 1,270
- **Imbalanced Dataset** with overlapping SCC and BCC labels.

---

## **Project Workflow**

### **1. Image Preprocessing**
- **Hair Removal:** 
  - Blackhat filter using multiple oriented structural elements + thresholding.
- **Color Normalization:** 
  - Consistent color balance to minimize lighting and color variation.
- **Region of Interest (ROI):**
  - Extract ROI based on pixel mean values surpassing a threshold.

### **2. Feature Extraction**
Extracted **842 features** categorized into:
1. **Color Features:** 
   - Stats (min, max, kurtosis, median, percentiles, normalized std).
   - Moments (mean, skewness, variance) across RGB, HSV, and LAB color spaces.
   - Histograms and grayscale entropy.
2. **Texture Features:**
   - Local Binary Pattern (LBP) from the blue channel.
   - Gray Level Co-occurrence Matrix (GLCM).
   - Haralick features.
3. **Gradient Features:**
   - Wavelet features from grayscale images.
   - Histogram of Gradients (HOG) reduced via PCA.

### **3. Machine Learning Classification**
- **Classifiers Implemented:**
  - Random Forest
  - LightGBM
  - XGBoost
  - Support Vector Machine (SVM)
- **Ensemble Techniques:**
  - Stacking
  - Majority Voting

---

## **Evaluation Metrics**
### **Binary Classification**
- **Accuracy** and **F1 Score**

### **Multi-class Classification**
- **Kappa Score**
- **Balanced Accuracy**

---

## **Key Findings**
- **Significant Features:** Color and texture features were most relevant for the task.
- **Imbalance Issues:** Severe overlap between SCC and BCC labels limited classification performance.
- **Feature Selection:** Did not degrade performance, even with reduced features.

---

## **Future Scope**
1. Development of a **multi-resolution framework**.
2. Feature extraction after lesion segmentation using **deep learning techniques**.

---

## **References**
1. [Sampling Algorithms Experimental Analysis](https://github.com/newaz-aa/Sampling-algorithms-experimental-analysis)
2. [Skin Cancer Classification Using Image Processing and Machine Learning](https://doi.org/10.1109/IBCAST51254.2021.9393198)
3. [SMOTE Variants Documentation](https://smote-variants.readthedocs.io/en/latest/oversamplers.html)
4. [UMAP for Dimension Reduction](https://umap-learn.readthedocs.io/en/latest/)
5. [Imbalanced-learn Documentation](https://imbalanced-learn.org/stable/)
