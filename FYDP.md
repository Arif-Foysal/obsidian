#uiu #FYDP #software-engineering #Machine-Learning 

[[fydp pre defence presentation]]

## ML For everybody
	https://www.youtube.com/watch?v=i_LwzRVP7bg&t=6824s

## [[FYDP workload distribution]]

[[Reducing traffic using computer vision]]




## Defining Complex Engineering Problem:

## AI Dermatologist Agent
https://www.geeksforgeeks.org/deep-learning/skin-cancer-detection-using-tensorflow/

https://thepythoncode.com/article/skin-cancer-detection-using-tensorflow-in-python
	- 

### How to improve a notebook for your paper
##### 1. ✅ **Understand What the Notebook Does**

- Study the original notebook deeply:
    - What dataset does it use?
    - Which model(s) does it train?
    - What evaluation metrics are applied?
    - Any data augmentation or preprocessing?
- Identify its **goals and limitations**.

>current notebooks:

##### **InceptionV3:**

**dataset**: ISIC Archive

**Model: -**
Trained on a single model based on the InceptionV3 architecture. It utilizes a pre-trained InceptionV3 model from TensorFlow Hub as a feature extractor and adds a single dense layer with a sigmoid activation for binary classification (benign vs. malignant).

**Evaluation Matrics: -** 
- **Accuracy:** The overall percentage of correctly classified images.
- **Loss:** Binary cross-entropy, a common loss function for binary classification.
- **Confusion Matrix:** A table showing the counts of true positive, true negative, false positive, and false negative predictions.
- **ROC AUC:** The Area Under the Receiver Operating Characteristic curve, which measures the model's ability to distinguish between the two classes.
- **Sensitivity (Recall):** The proportion of actual malignant cases that are correctly identified.
- **Specificity:** The proportion of actual benign cases that are correctly identified.

**Data Augmentation or Preprocessing:**
	The notebook performs the following preprocessing steps:
- **Image Decoding and Resizing:** Images are decoded from JPEG format, converted to float32, and resized to 299x299 pixels, which is the input size expected by the InceptionV3 model.
- **Data Loading and Batching:** The data is loaded using `tf.data.Dataset` from CSV files containing file paths and labels. The datasets are then shuffled, batched, and prefetched for efficient training.
- **Caching:** The processed datasets are cached to improve training speed.

**Limitations:**
- **Limited Data Augmentation:** The lack of data augmentation might lead to the model overfitting on the training data and performing poorly on unseen data.
- **Class Imbalance:** The dataset might have a class imbalance (unequal number of benign and malignant images), which could affect the model's performance, especially sensitivity and specificity. While the code includes metrics to assess this, no techniques are used to mitigate the imbalance.
- **Fixed Threshold:** The prediction threshold is fixed at 0.5 for initial evaluation and then manually adjusted to 0.23 for further evaluation. A more systematic approach, such as finding the optimal threshold based on the ROC curve or other metrics, could improve performance.
- **Single Model:** The notebook only trains a single model architecture. Exploring other architectures or ensemble methods could potentially lead to better results.

##### Efficientnet v7

Based on the notebook, here's a breakdown of the project:

- **Dataset:** The notebook uses a dataset of images for cancer detection, stored in the `train_cancer` directory, with subdirectories for 'benign' and 'malignant' cases.
- **Model:** The notebook utilizes a pre-trained `EfficientNetB7`model as a base, with its layers frozen, and adds a custom dense layer with Batch Normalization and Dropout for the classification task.
- **Evaluation Metrics:** The model is evaluated using 'loss' and 'AUC' (Area Under the Curve) metrics.
- **Data Augmentation/Preprocessing:** The notebook performs preprocessing on the images, including decoding JPEG files, resizing them to 224x224 pixels, and normalizing pixel values by dividing by 255. It also creates a `tf.data.Dataset` for training and validation with batching and prefetching.

**Goals and Limitations:**

- **Goal:** The primary goal is to train a model to classify images as either 'benign' or 'malignant' for cancer detection.
- **Limitations:** The current model architecture uses a flattened output from the pre-trained EfficientNetB7 before the dense layers, which discards the spatial information learned by the convolutional base. This is likely contributing to the poor performance seen in the training history where validation AUC is low and validation loss is high. Additionally, the dataset size is relatively small (270 images), which can limit the model's ability to generalize. The class distribution is also imbalanced, with more benign images than malignant, which could affect training.

##### 2. ✍️ **Credit the Original Notebook**

Always acknowledge the Kaggle author and notebook in:

- Your code (e.g., in the first cell: “Based on notebook by @username” with a link)
- Your thesis or paper references
##### 3. 🔧 **Ways to Improve or Extend It**
Choose 2–4 of the following improvements (depending on your skill and goals):
###### 🔄 a) **Use a Better Model**
- Try models not included in the original: e.g., switch from ResNet34 to EfficientNetB0, ConvNeXt, or Vision Transformers.
###### 📊 b) **Add New Evaluation Metrics**
- Include metrics like ROC-AUC, precision-recall curve, F1-score per class, confusion matrix.

  ##### 📈 In Your Paper or Project, Include:
1. **Confusion matrix**
2. **F1-score per class**
3. **ROC curve with AUC**
4. **PR curve**
5. Discussion on **which classes the model struggles with**
###### 🧠 c) **Use Transfer Learning or Fine-tuning**
- If the original used frozen layers, try fine-tuning the full model.
- Change the classifier head structure.
###### 🧼 d) **Improve Data Preprocessing**

- Add augmentation: rotation, brightness shift, flipping, cutmix, etc.
- Normalize better or handle class imbalance.
#### 📈 e) **Visualize More**

- Add Grad-CAM or heatmap visualizations.
    
- Show ROC curves, confusion matrix, training vs validation loss curves.
    

#### 💾 f) **Use Another Dataset or Merge Datasets**

- Combine ISIC 2017 + HAM10000 to increase diversity.
    
- Or do data cleaning/improvement.
    

#### 🧪 g) **Perform Comparative Experiments**

- Train 3 models and compare.
    
- Try training with/without augmentation and compare accuracy.
    
### 4. 🗃️ **Modularize the Notebook into Scripts**

For a professional look:
- Convert your notebook into `.py` files for:
    - data preprocessing
    - training
    - evaluation
- This shows software engineering maturity.
    
### 5. 📄 **Write About It in Your Thesis**
Include sections like:
- Problem & Dataset
- Model Architecture (your changes)
- Improvements over baseline (Kaggle)
- Evaluation & Discussion
- Visualizations
- Limitations & Future Work
## 🧠 Example:
You find a Kaggle notebook that:
- Uses ResNet50
- Uses basic augmentation
- Shows only accuracy

**You improve it by:**
- Switching to EfficientNetB0
- Adding F1-score, Grad-CAM, ROC-AUC
    
- Training on a merged dataset (ISIC + HAM10000)
    
- Packaging it with FastAPI for inference
    







# Lab:01
### Washington Accord
https://www.internationalengineeringalliance.org/accords/washington

![[Smart Irrigation System]]




![[AI Based Medical Diagnosis System]]




## Vapi Voice Assistant for Booking Appointments

