# Image Classification using Convolutional Neural Networks (CNN)

**Author:** SATWIK TELANG

**Registration Number:** 23BAI11046

**Application Number:** IN26011013

**Batch Number:** 1A

**Email ID:** satwik.23bai11046@vitbhopal.ac.in

---

## Objective

The objective of this project is to develop a Convolutional Neural Network (CNN) using TensorFlow/Keras to classify pet images into **Cats and Dogs** to support automated animal identification.

---

## Dataset Link

- [Kaggle: Dog and Cat Classification Dataset](https://www.kaggle.com/datasets/bhavikjikadara/dog-and-cat-classification-dataset)

---

## Libraries Used

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `tensorflow / keras`
- `scikit-learn`
- `Pillow`
- `kaggle`

---

## Methodology

### 1. Data Understanding

Analyzed the binary classification dataset containing **24,998 valid RGB images**:

- **12,499 Cats**
- **12,499 Dogs**

Sample images were also visualized to understand the dataset.

### 2. Data Preprocessing

- Filtered unreadable/corrupted files.
- Resized images to **128 × 128 pixels**.
- Normalized pixel intensity values to the **[0, 1]** range.
- Split the dataset into:
  - **80% Training:** 19,998 images
  - **20% Testing:** 5,000 images
- Created batch image generators using `ImageDataGenerator`.

### 3. CNN Architecture

The Convolutional Neural Network consists of:

- **Conv2D Block 1:** 32 filters, `(3 × 3)` kernel, ReLU activation + MaxPooling2D `(2 × 2)`
- **Conv2D Block 2:** 64 filters, `(3 × 3)` kernel, ReLU activation + MaxPooling2D `(2 × 2)`
- **Conv2D Block 3:** 128 filters, `(3 × 3)` kernel, ReLU activation + MaxPooling2D `(2 × 2)`
- **Flatten Layer**
- **Dense Layer:** 128 neurons with ReLU activation
- **Output Layer:** 1 neuron with Sigmoid activation

### 4. Compilation & Training

- **Optimizer:** Adam
- **Loss Function:** Binary Crossentropy
- **Training Epochs:** 10

### 5. Evaluation

The trained CNN model was evaluated using:

- Test Accuracy
- Test Loss
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Accuracy/Loss graphs per epoch

---

## CNN Architecture Summary

| Layer | Type | Output Shape | Param # |
|---|---|---|---:|
| conv2d | Conv2D (32, 3×3) | (None, 126, 126, 32) | 896 |
| max_pooling2d | MaxPooling2D (2×2) | (None, 63, 63, 32) | 0 |
| conv2d_1 | Conv2D (64, 3×3) | (None, 61, 61, 64) | 18,496 |
| max_pooling2d_1 | MaxPooling2D (2×2) | (None, 30, 30, 64) | 0 |
| conv2d_2 | Conv2D (128, 3×3) | (None, 28, 28, 128) | 73,856 |
| max_pooling2d_2 | MaxPooling2D (2×2) | (None, 14, 14, 128) | 0 |
| flatten | Flatten | (None, 25088) | 0 |
| dense | Dense (128, ReLU) | (None, 128) | 3,211,392 |
| dense_1 | Dense (1, Sigmoid) | (None, 1) | 129 |

---

## Results

- **Test Accuracy:** 85.20%
- **Test Loss:** 0.7194
- **Precision:** 84.43%
- **Recall:** 86.32%
- **F1-Score:** 85.36%

---

## Conclusion

The **3-layer CNN** effectively extracts spatial features from pet images and successfully classifies them into cats and dogs with an **85.20% test accuracy**.

The results demonstrate that CNNs can effectively perform binary image classification by automatically learning important visual features from images.

Further improvements such as **data augmentation, dropout, batch normalization, transfer learning, and hyperparameter tuning** could help improve model performance and generalization on unseen images.
