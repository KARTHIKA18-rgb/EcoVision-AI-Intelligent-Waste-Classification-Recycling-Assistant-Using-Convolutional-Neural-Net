# ♻️ Garbage Classification Using CNN

## 📌 Project Overview
This project uses a Convolutional Neural Network (CNN) to classify waste images into six categories: **Cardboard, Glass, Metal, Paper, Plastic, and Trash**. The model helps automate waste segregation, improving recycling efficiency and supporting sustainable waste management.

---

## 🎯 Objectives
- Build a deep learning model for waste classification.
- Classify images into six waste categories.
- Evaluate model performance using accuracy and loss metrics.
- Demonstrate the application of AI in smart waste management.

---

## 📂 Dataset

The dataset consists of six waste categories:

| Class | Description |
|--------|-------------|
| 📦 Cardboard | Cardboard boxes and packaging materials |
| 🍾 Glass | Glass bottles, jars, and containers |
| 🥫 Metal | Metal cans and metallic waste |
| 📄 Paper | Newspapers, books, paper sheets, cartons |
| 🥤 Plastic | Plastic bottles, containers, wrappers |
| 🗑️ Trash | Mixed waste that doesn't belong to other categories |

### Dataset Features
- Image Classification Dataset
- 6 Classes
- RGB Images
- Used for CNN-based image classification
- Train/Test split for model evaluation

---

## 🛠️ Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- OpenCV
- Scikit-learn
- Jupyter Notebook

---

## 📊 Data Preprocessing

- Image Loading
- Image Resizing
- Label Encoding
- Normalization
- Train-Test Split
- Data Augmentation (if applied)

---

## 🧠 CNN Model Architecture

The CNN model consists of:

- Convolution Layers
- ReLU Activation
- MaxPooling Layers
- Flatten Layer
- Dense Layers
- Softmax Output Layer

---

## 📈 Model Evaluation

Evaluation Metrics:
- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- Confusion Matrix
- Classification Report

---

## 📊 Data Visualizations

The project includes visualizations such as:

- ✅ Class Distribution
- ✅ Sample Images from Each Category
- ✅ Training Accuracy vs Validation Accuracy
- ✅ Training Loss vs Validation Loss
- ✅ Confusion Matrix
- ✅ Prediction Results on Test Images

### Insights from Visualizations

- Dataset contains six distinct waste categories.
- CNN learns progressively with increasing training accuracy.
- Validation accuracy follows training accuracy, indicating good generalization.
- Loss decreases over epochs, showing effective learning.
- Confusion Matrix highlights classes with higher and lower prediction accuracy.
- Some misclassification occurs between visually similar classes such as Plastic and Trash.

---

## 🚀 Results

- Successfully classified waste into six categories.
- Achieved high classification accuracy using CNN.
- Demonstrates the effectiveness of deep learning for automated waste segregation.

---

## 📁 Project Structure

```
Garbage-Classification/
│
├── Dataset/
├── Notebook.ipynb
├── Model/
├── Images/
├── README.md
└── requirements.txt
```

---

## 🔮 Future Improvements

- Apply Transfer Learning (ResNet50, EfficientNet, MobileNetV2)
- Increase dataset size
- Deploy using Streamlit or Flask
- Real-time webcam-based garbage classification
- Hyperparameter tuning for better accuracy

---
## ✅ Conclusion

This project demonstrates the effectiveness of Convolutional Neural Networks (CNNs) in automatically classifying waste into six categories: **Cardboard, Glass, Metal, Paper, Plastic, and Trash**. By leveraging deep learning techniques, the model achieves reliable image classification performance, making waste segregation faster and more accurate. The project highlights the potential of AI in promoting efficient recycling and sustainable waste management. With further improvements such as transfer learning, larger datasets, and real-time deployment, the system can be extended into a practical smart waste classification solution.
