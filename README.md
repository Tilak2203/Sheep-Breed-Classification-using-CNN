# 🐑 Sheep Breed Classification Using CNN

This project leverages **Convolutional Neural Networks (CNNs)** and **transfer learning** (ResNet50 and VGG19) to classify images of **four sheep breeds**. It demonstrates a complete deep learning workflow — from preprocessing image data to building, training, and evaluating models using TensorFlow and Keras.

---

## 📂 Dataset

- Images of sheep faces categorized into 4 breeds:
  - **Marino**
  - **White Suffolk**
  - **Poll Dorset**
  - **Suffolk**
- Images are resized to **150×150** pixels
- Pixel values normalized to **[0, 1]**
- [Download Dataset from Google Drive](https://drive.google.com/drive/folders/175QRkvdWVVf94Cf2bZwUm89Ik7XtkdX5?usp=sharing)


---

## 🧪 Project Workflow

### 1. Data Preprocessing
- Loaded images using OpenCV (`cv2`)
- Resized to 150×150 pixels
- Normalized pixel values
- Encoded breed names to integers → one-hot encoding

### 2. Train-Test Split
- Stratified split (80% training, 20% testing)

### 3. Model Architecture
- **ResNet50** and **VGG19** used as **feature extractors**
- Removed original top layers (`include_top=False`)
- Added custom classifier: `Flatten → Dense(4, activation='softmax')`
- Base layers **frozen** during training

### 4. Training Setup
- **Loss Function**: `categorical_crossentropy`
- **Optimizer**: `Adam`
- **Batch Size**: 64
- **Epochs**: 25 (with early stopping)
- **Callbacks**:
  - `ModelCheckpoint` – Saves best model
  - `EarlyStopping` – Prevents overfitting

### 5. Evaluation
- Accuracy and loss plots
- Confusion matrix
- Classification report (Precision, Recall, F1-Score)
- Sample predictions

---

## 📊 Results

| Model    | Accuracy | Notes                  |
|----------|----------|------------------------|
| ResNet50 | ~93%     | Best overall performer |
| VGG19    | ~91–92%  | Competitive performance|

---
<img width="1725" height="496" alt="image" src="https://github.com/user-attachments/assets/8e6d19e5-2111-4f2a-9806-49d283942758" />

<img width="1730" height="515" alt="image" src="https://github.com/user-attachments/assets/22e45e9d-405b-43d1-a6a1-fb1a9308e275" />


