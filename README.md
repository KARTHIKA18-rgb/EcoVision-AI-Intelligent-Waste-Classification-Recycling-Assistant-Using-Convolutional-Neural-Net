# ♻️ EcoVision AI – Intelligent Waste Classification & Recycling Assistant Using CNN

## 📌 Project Overview

**EcoVision AI** is an intelligent waste classification system developed using **Convolutional Neural Networks (CNN)**, Computer Vision, and Deep Learning.

The system analyzes waste images and automatically classifies them into different categories. The main objective is to support **automated waste segregation, recycling, and sustainable waste management** by reducing the need for manual sorting.

The project demonstrates how Artificial Intelligence and Computer Vision can be applied to a real-world environmental problem.

---

## 🎯 Objectives

* Develop a CNN model for automatic waste image classification.
* Automate the waste segregation process.
* Improve the efficiency of waste classification using Deep Learning.
* Preprocess and prepare waste images for CNN training.
* Classify waste into predefined categories.
* Evaluate the model using accuracy, precision, recall, F1-score, and confusion matrix.
* Support recycling and sustainable waste management.
* Demonstrate the practical application of AI in environmental management.

---

## 🗂️ Dataset

The project uses a labeled image dataset containing different types of garbage.

### Waste Categories

The CNN model in this notebook is trained on **6 waste categories**:

| Class        | Description                        |
| ------------ | ---------------------------------- |
| 📦 Cardboard | Cardboard-based waste materials    |
| 🥂 Glass     | Glass waste items                  |
| 🔩 Metal     | Metal-based waste                  |
| 📄 Paper     | Paper waste                        |
| 🧴 Plastic   | Plastic waste                      |
| 🗑️ Trash    | General non-recyclable/mixed trash |

The notebook also documents a broader objective involving additional categories, but the implemented CNN model and final evaluation use **6 classes**.

### Dataset Summary

* **Total Images:** 2,527
* **Training Images:** 1,818
* **Validation Images:** 203
* **Testing Images:** 506
* **Image Input Size:** 128 × 128 × 3
* **Image Format:** JPEG
* **Image Type:** RGB

## The notebook performs folder-level inspection and checks the image structure before model development.

## 🧰 Tools & Technologies Used

### Programming Language

* **Python**

### Deep Learning

* **TensorFlow**
* **Keras**
* **Convolutional Neural Network (CNN)**

### Computer Vision & Image Processing

* **OpenCV**
* **PIL / Pillow**

### Data Processing

* **NumPy**
* **Pandas**

### Data Visualization

* **Matplotlib**

### Machine Learning Evaluation

* **Scikit-learn**

### Development Environment

* **Google Colab / Jupyter Notebook**

---

## 🔄 Project Workflow

```text
Waste Image Dataset
        ↓
Dataset Inspection
        ↓
Image Visualization
        ↓
Image Shape & Format Checking
        ↓
Image Preprocessing
        ↓
Train / Validation / Test Split
        ↓
CNN Model Creation
        ↓
Model Compilation
        ↓
CNN Training
        ↓
Data Augmentation
        ↓
Model Evaluation
        ↓
Classification Report
        ↓
Confusion Matrix
        ↓
New Image Prediction
        ↓
Waste Category
```

---

## 🔍 Data Understanding & Visualization

Before training the CNN, the dataset was explored to understand the structure and quality of the images.

### 1. Folder Inspection

Each waste category folder was inspected using Python to verify the available images.

This helped confirm that the dataset was organized according to waste categories.

### 2. Image Visualization

Sample images from different waste classes were visualized to understand:

* Appearance of different waste categories.
* Variation in image backgrounds.
* Different object orientations.
* Visual differences between waste types.
* Whether images were correctly assigned to their classes.

The notebook specifically uses visualization to verify class assignments and understand the dataset before training.

### 3. Image Shape and Format Analysis

The notebook checks image dimensions and format.

An example image was found to have:

```text
Shape: (384, 512, 3)
Format: JPEG
```

The images are subsequently resized to **128 × 128 × 3** for CNN processing.

### 📊 What the Visualizations Helped Understand

The data visualization and inspection helped identify:

* Different visual characteristics of each waste category.
* Variations in image size and orientation.
* The importance of resizing images before CNN training.
* The need for consistent image dimensions.
* Possible similarities between visually related waste categories.
* The importance of checking image quality before model training.

---

## 🧹 Data Preprocessing

The images are prepared before being provided to the CNN.

### Main preprocessing steps:

1. Load images from category folders.
2. Read images using OpenCV/PIL.
3. Resize images to:

```text
128 × 128 × 3
```

4. Convert image data into NumPy arrays.
5. Normalize pixel values.
6. Encode class labels.
7. Split the dataset into training, validation, and testing sets.

The resulting datasets are:

```text
X_train : (1818, 128, 128, 3)
X_val   : (203, 128, 128, 3)
X_test  : (506, 128, 128, 3)
```

---

## 🧠 CNN Architecture

The project uses a custom CNN built using Keras Sequential API.

### Architecture

```text
Input Image
128 × 128 × 3
      ↓
Conv2D – 8 Filters
      ↓
MaxPooling2D
      ↓
Conv2D – 16 Filters
      ↓
MaxPooling2D
      ↓
Conv2D – 32 Filters
      ↓
MaxPooling2D
      ↓
Dropout
      ↓
Flatten
      ↓
Dense – 50 Neurons
      ↓
Dropout
      ↓
Dense – 6 Classes
      ↓
Softmax Output
```

The implemented model contains **412,668 trainable parameters**.

### CNN Components

* **Conv2D:** Extracts visual features from waste images.
* **ReLU:** Introduces non-linearity.
* **MaxPooling:** Reduces spatial dimensions.
* **Dropout:** Helps reduce overfitting.
* **Flatten:** Converts feature maps into a one-dimensional representation.
* **Dense Layer:** Learns higher-level patterns.
* **Softmax:** Produces class probabilities.

---

## ⚙️ Model Compilation

The CNN is compiled using:

```text
Optimizer  : Adam
Learning Rate : 0.001
Loss       : Categorical Crossentropy
Metric     : Accuracy
```

These settings prepare the CNN for multi-class classification.

---

## 🚀 Model Training

The initial CNN model was trained for:

```text
Epochs    : 30
Batch Size: 10
```

A `ModelCheckpoint` callback was also used to save the best model during training.

### Initial Training Result

```text
Training Accuracy : 99.615%
Test Accuracy     : 65.02%
```

The large difference between training and test performance indicated that the model was learning the training images much better than unseen images.

---

## 🔄 Data Augmentation

To improve generalization, `ImageDataGenerator` was used.

### Augmentation Techniques

* Rotation
* Width shifting
* Height shifting
* Shearing
* Zooming
* Horizontal flipping

```text
rotation_range = 20
width_shift_range = 0.2
height_shift_range = 0.2
shear_range = 0.2
zoom_range = 0.2
horizontal_flip = True
```

Data augmentation creates variations of training images and helps the CNN learn more robust visual features rather than memorizing the original training images.

---

## 📈 Training After Data Augmentation

After applying augmentation, the training process showed improved validation performance.

The best validation accuracy observed during the augmentation-based training was approximately:

```text
Validation Accuracy : 72.91%
```

The validation accuracy improved from the earlier training stages and reached its highest recorded value around epoch 28.

---

## 📊 Model Evaluation

The trained model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

These metrics provide a more detailed understanding of classification performance across different waste categories.

### Final Recorded Evaluation

```text
Training Accuracy : 89.99%
Test Accuracy     : 69.37%
Test Loss         : 0.8666
```

The final recorded test accuracy after augmentation was **69.37%**.

---

## 📋 Classification Report

The recorded classification report shows the following performance:

| Class   | Precision | Recall | F1-Score | Support |
| ------- | --------: | -----: | -------: | ------: |
| Class 0 |      0.80 |   0.79 |     0.80 |      62 |
| Class 1 |      0.71 |   0.56 |     0.63 |     105 |
| Class 2 |      0.52 |   0.65 |     0.58 |      75 |
| Class 3 |      0.75 |   0.87 |     0.81 |     140 |
| Class 4 |      0.72 |   0.62 |     0.67 |      95 |
| Class 5 |      0.59 |   0.45 |     0.51 |      29 |

### Overall

```text
Accuracy      : 69%
Macro F1      : 0.66
Weighted F1   : 0.69
```

The classification report indicates that some waste categories are easier for the CNN to recognize than others.

---

## 🔲 Confusion Matrix Analysis

The confusion matrix was used to identify where the CNN makes classification errors.

The results show that:

* Some categories have strong correct predictions.
* Class 3 achieved relatively strong recognition with **87% recall**.
* Class 5 had comparatively lower recall at **45%**.
* There are noticeable misclassifications between some visually similar waste categories.
* The model performs better on categories with more distinctive visual features.

This analysis helps identify which classes may require additional training images or improved preprocessing.

---

## 🖼️ New Image Prediction

The trained CNN can also classify a new waste image.

The prediction process includes:

```text
New Image
    ↓
Resize to 128 × 128
    ↓
Normalize Image
    ↓
CNN Prediction
    ↓
Class Probabilities
    ↓
Highest Probability
    ↓
Predicted Waste Category
```

The notebook demonstrates prediction on new images such as glass and cardboard samples.

---

## 📊 Key Insights From Data Visualization & Analysis

The exploratory analysis and model results provide several useful insights:

### 🔹 1. Waste images have significant visual variation

Images contain different orientations, backgrounds, and appearances. This makes image preprocessing and augmentation important for robust classification.

### 🔹 2. Image dimensions need standardization

The original images can have different dimensions, so resizing them to **128 × 128 × 3** provides a consistent input format for the CNN.

### 🔹 3. Some waste categories are visually easier to identify

The classification report shows that certain classes achieve higher precision, recall, and F1-score than others.

### 🔹 4. Visually similar classes can be confused

The confusion matrix shows that some classes are incorrectly predicted as other classes, indicating similarities in their visual characteristics.

### 🔹 5. Data augmentation improves generalization

Augmentation increased image diversity and helped improve validation performance compared with the initial training process.

### 🔹 6. The model shows a generalization gap

The final recorded training accuracy was higher than the test accuracy, indicating that there is still room to improve generalization to unseen waste images.

---

## 🌱 Real-World Applications

EcoVision AI can serve as a foundation for:

* ♻️ Automated waste segregation
* 🗑️ Smart dustbins
* 🏭 Recycling facilities
* 🏙️ Smart city waste management
* 📱 Waste classification mobile applications
* 📷 Camera-based waste recognition systems
* 🌍 Sustainable waste management solutions

The notebook also identifies smart dustbins, recycling plants, smart-city systems, and future camera/web/mobile deployment as possible extensions.

---

## 🔮 Future Enhancements

The current project can be improved by:

* Using a larger and more balanced dataset.
* Increasing the number of training images for underrepresented classes.
* Applying stronger data augmentation.
* Using Transfer Learning models such as MobileNet, EfficientNet, or ResNet.
* Hyperparameter tuning.
* Adding real-time camera-based classification.
* Developing a Streamlit web application.
* Developing a mobile application.
* Integrating the model with smart-bin hardware.
* Adding recycling recommendations based on the predicted waste category.

---

## 📁 Project Structure

```text
EcoVision-AI/
│
├── Garbage_Classification_Using_CNN.ipynb
├── README.md
│
├── dataset/
│   ├── cardboard/
│   ├── glass/
│   ├── metal/
│   ├── paper/
│   ├── plastic/
│   └── trash/
│
└── saved_model/
    └── model.weights.best.keras
```

> **Note:** The dataset itself may not be included in the GitHub repository because image datasets can be large. The notebook contains the dataset path used during development.

---

## 🛠️ Installation

Install the required Python libraries:

```bash
pip install tensorflow keras numpy pandas matplotlib opencv-python pillow scikit-learn
```

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <your-repository-link>
```

### 2. Open the notebook

Open:

```text
Garbage_Classification_Using_CNN.ipynb
```

using:

* Google Colab
* Jupyter Notebook
* JupyterLab

### 3. Add the dataset

Place the waste image dataset in the required directory and update the dataset path in the notebook.

### 4. Run the notebook

Execute the notebook cells sequentially to:

```text
Load Dataset
→ Explore Images
→ Preprocess
→ Train CNN
→ Augment Data
→ Evaluate Model
→ Predict New Images
```

---

## 📌 Results Summary

| Metric                  |        Result |
| ----------------------- | ------------: |
| Number of Classes       |             6 |
| Total Images            |         2,527 |
| Training Images         |         1,818 |
| Validation Images       |           203 |
| Test Images             |           506 |
| Input Size              | 128 × 128 × 3 |
| CNN Parameters          |       412,668 |
| Final Training Accuracy |        89.99% |
| Final Test Accuracy     |        69.37% |
| Macro F1-Score          |          0.66 |
| Weighted F1-Score       |          0.69 |

---

## 💡 Conclusion

**EcoVision AI** demonstrates the use of Convolutional Neural Networks for automated waste classification. The project combines **Data Science, Computer Vision, and Deep Learning** to address the practical challenge of waste segregation.

The CNN successfully learns visual patterns from waste images and can classify new images into predefined waste categories. The use of data augmentation improves the model's ability to generalize, while the classification report and confusion matrix provide insights into class-level performance.

Although the current model achieves a test accuracy of **69.37%**, further improvements through larger datasets, better class balancing, transfer learning, and hyperparameter tuning can make the system more robust for real-world deployment.

---

## 👩‍💻 Technologies

```text
Python
TensorFlow
Keras
CNN
Computer Vision
OpenCV
Pillow
NumPy
Pandas
Matplotlib
Scikit-learn
Google Colab
```
