# Indian Coin Classification using CNN

A deep learning project that identifies Indian coins from images using **Convolutional Neural Networks (CNN)** and **MobileNetV2 transfer learning**.

The model classifies images into four Indian coin denominations:

* ₹1
* ₹2
* ₹5
* ₹10

## 📌 Project Overview

The goal of this project is to build an image classification model that can automatically recognize the denomination of an Indian coin from a photograph.

The project follows a complete deep-learning workflow:

**Dataset → Image Preprocessing → Data Augmentation → Model Training → Validation → Prediction**

Two approaches were explored:

1. A custom CNN model
2. MobileNetV2 with transfer learning

The MobileNetV2 approach produced better validation performance than the initial custom CNN.

## 🗂️ Dataset

The dataset contains **1,808 JPG images** belonging to four coin classes.

| Coin | Class    |
| ---- | -------- |
| ₹1   | 1 Rupee  |
| ₹2   | 2 Rupee  |
| ₹5   | 5 Rupee  |
| ₹10  | 10 Rupee |

Dataset split:

* **Training images:** 1,447
* **Validation images:** 361

## 🧠 Model

### Custom CNN

The first model was built using convolutional and pooling layers.

However, the model showed signs of **overfitting**:

* Training accuracy: approximately **91%**
* Validation accuracy: approximately **39%**

This indicated that the model learned the training images much better than unseen validation images.

### MobileNetV2 Transfer Learning

To improve performance, **MobileNetV2** was used as a pretrained feature extractor.

The model uses:

* MobileNetV2
* Image resizing
* Data augmentation
* Dense classification layer
* Softmax output for four classes

The MobileNetV2 model achieved approximately:

* **Training accuracy:** 70.6%
* **Validation accuracy:** 65.9%

This was a significant improvement in generalization compared with the initial CNN.

## 🔄 Data Augmentation

Image augmentation was used to help the model handle variations in coin images.

The training pipeline includes image transformations such as:

* Random rotation
* Random zoom
* Random translation
* Image preprocessing

This helps the model learn features that are less dependent on the exact position or orientation of the coin.

## 🔍 Prediction

After training, the model can take a new coin image and predict its denomination.

Example output:

```text
Predicted Coin: 5 Rupee
Confidence: 48.70%
```

The prediction demonstrates that the trained model can classify a previously unseen coin image.

## 🛠️ Technologies Used

* Python
* TensorFlow
* Keras
* MobileNetV2
* NumPy
* Matplotlib
* Google Colab / Jupyter Notebook
* Git
* GitHub

## 📁 Project Structure

```text
indian-coin-classification-cnn/
│
├── indian-coin-classification-cnn.ipynb
├── README.md
├── dataset/
│   ├── 1 Rupee/
│   ├── 2 Rupee/
│   ├── 5 Rupee/
│   └── 10 Rupee/
│
└── model/
    └── coin_classification_model
```

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Muthuvanesh/indian-coin-classification-cnn.git
```

### 2. Open the notebook

Open:

```text
indian-coin-classification-cnn.ipynb
```

using **Google Colab** or **Jupyter Notebook**.

### 3. Install required libraries

```bash
pip install tensorflow numpy matplotlib
```

### 4. Load the dataset

Place the coin dataset in the appropriate dataset directory.

### 5. Train the model

Run the notebook cells sequentially to:

* Load images
* Preprocess the dataset
* Augment training
