### 1. **What dataset does it use?**

- **Dataset:**  
  The code uses the **HAM10000** dataset ("Human Against Machine with 10000 training images"), a large collection of multi-source dermatoscopic images of common pigmented skin lesions.
- **Source:**  
  Downloaded via the `kagglehub` package from Kaggle: `kmader/skin-cancer-mnist-ham10000`.
- **Contents:**  
  - 10,015 images in two directories (`HAM10000_images_part_1` and `HAM10000_images_part_2`).
  - Metadata CSV (`HAM10000_metadata.csv`) with fields such as `image_id`, `lesion_id`, `dx` (diagnosis/class), `age`, `sex`, and `localization`.
  - Seven diagnostic categories:  
    - bkl (Benign keratosis-like lesions)
    - bcc (Basal cell carcinoma)
    - akiec (Actinic keratoses)
    - vasc (Vascular lesions)
    - nv (Melanocytic nevi)
    - mel (Melanoma)
    - df (Dermatofibroma)
- **Class Imbalance:**  
  The dataset is highly imbalanced, with the "nv" class dominating.

---

### 2. **Which model(s) does it train?**

The code trains and evaluates four deep learning models for binary skin lesion classification (benign vs. malignant):

1. **Vision Transformer (ViT)**
   - `ViTForImageClassification` from HuggingFace Transformers.
   - Pretrained on ImageNet-21k, fine-tuned for this task.

2. **Swin Transformer**
   - `swin_tiny_patch4_window7_224` from the `timm` library.
   - Pretrained, fine-tuned for this task.

3. **EfficientNet-B0**
   - `efficientnet_b0` from the `timm` library.
   - Pretrained, fine-tuned for this task.

4. **ResNet50**
   - From `torchvision.models`.
   - Pretrained, with the final layer replaced for binary classification.

### 3. **What evaluation metrics are applied?**

The following metrics and visualizations are used to evaluate model performance:

- **Accuracy**
- **F1 Score** (weighted)
- **Confusion Matrix**
- **Classification Report** (precision, recall, F1, support)
- **ROC Curve** and **AUC (Area Under the Curve)**
- **Precision-Recall (PR) Curve** and **Average Precision (AP)**
- **Training/Validation Loss and Accuracy Curves** (for each model)
- **Bar Chart** comparing accuracy and F1 scores across models

---

### 4. **Any data augmentation or preprocessing?**

**Preprocessing:**
- **Metadata:**
  - Missing ages filled with the mean.
  - Missing sex filled with "unknown".
  - Age values clipped to [0, 100].
  - Sex and localization encoded numerically.
  - Labels grouped into binary classes:  
    - 0 = benign (`nv`, `bkl`, `df`, `vasc`)
    - 1 = malignant (`mel`, `bcc`, `akiec`)
- **Images:**
  - All images converted to RGB.

**Data Augmentation (for training set):**
- Resize to (256, 256), then random resized crop to (224, 224)
- Random horizontal flip (p=0.5)
- Random vertical flip (p=0.2)
- Random rotation (±15 degrees)
- Color jitter (brightness, contrast, saturation, hue)
- Normalization (ImageNet mean and std)

**Validation set:**  
- Only resized to (224, 224) and normalized (no augmentation).

---

If you need this in a specific format (e.g., for a paper section), let me know!