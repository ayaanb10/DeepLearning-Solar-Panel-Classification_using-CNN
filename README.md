# Solar Panel Defect Classification using Deep Learning

## Overview

This project focuses on building a deep learning model to automatically detect defects in solar panels using image classification.

Solar panels often suffer from efficiency loss due to:

* Dust accumulation
* Bird droppings
* Snow coverage
* Physical damage
* Electrical damage

Manual inspection is time-consuming and inefficient. This project uses AI-based automation to classify solar panel conditions from images.

---

## Problem Statement

To develop a multi-class image classification model that can accurately classify solar panel conditions into different defect categories.

---

## Dataset Information

* Source: Kaggle – Solar Panel Images
* Total Images: ~869
* Type: Multi-class classification

### Classes (6)

* Clean
* Dusty
* Bird-drop
* Electrical-damage
* Physical-Damage
* Snow-Covered

### Challenges

* Small dataset
* Class imbalance
* Noisy real-world images
* Variation in image resolution

---

## Model Used

### MobileNetV2 (Transfer Learning)

* Pretrained on ImageNet
* Lightweight and efficient
* Suitable for small datasets

### Custom Classification Head

* GlobalAveragePooling
* Dense layer (ReLU activation)
* Dropout for regularization
* Output layer (Softmax – 6 classes)

---

## Data Preprocessing

* Image resizing to 224 × 224
* Normalization
* Train-validation split (80:20)

### Data Augmentation

* Rotation
* Zoom
* Horizontal flip
* Brightness adjustment
* Shear transformation

---

## Handling Class Imbalance

* Used class weights (sklearn)
* Helps improve learning for minority classes

---

## Training Strategy

### Phase 1:

* Freeze base MobileNetV2 layers
* Train only custom layers

### Phase 2:

* Fine-tune entire model
* Improve feature learning

---

## Results

* Training Accuracy: ~80–83%
* Validation Accuracy: ~75–80%

### Evaluation Metrics

* Accuracy graphs
* Confusion matrix
* Classification report

---

## Observations

* Good performance on majority classes
* Lower accuracy for:

  * Physical damage
  * Electrical damage
* Slight overfitting due to small dataset

---

## Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib
* Scikit-learn

---

## Project Structure

```
Solar-Panel-Classification/
│── data/
│── notebooks/
│── models/
│── results/
│── README.md
```

---

## How to Run

### 1. Install Dependencies

```
pip install tensorflow numpy matplotlib scikit-learn
```

### 2. Download Dataset

Use Kaggle API:

```
kaggle datasets download -d pythonafroz/solar-panel-images
```

### 3. Run the Model

```
python train.py
```

---

## Future Improvements

* Use larger dataset
* Apply advanced models like EfficientNet
* Improve class balancing techniques
* Deploy as a web application

---

## Authors

* Anjali Ashtankar (Roll No: 16014223012)
* Ayaan Banatwalla (Roll No: 16014223025)

---

## Support

If you like this project, give it a star on GitHub!
