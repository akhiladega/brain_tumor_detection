# Quantum Brain Tumor Detection

This project implements a hybrid quantum-classical deep learning model
for detecting brain tumors from MRI images. The architecture integrates
a convolutional neural network with a variational quantum circuit to
explore quantum-enhanced feature learning for medical image
classification.

------------------------------------------------------------------------

## Overview

The system combines classical deep learning and quantum machine learning
techniques. MRI images are first processed using a convolutional neural
network backbone to extract features. These features are then embedded
into a quantum circuit where variational quantum layers perform
additional feature transformation before classification.

------------------------------------------------------------------------

## Model Architecture

### Classical Backbone

-   EfficientNet-B0 used for feature extraction
-   Modified to accept grayscale MRI images
-   Feature compression layer before quantum embedding

### Quantum Layer

-   4-qubit variational quantum circuit
-   AngleEmbedding used for encoding classical features
-   StronglyEntanglingLayers used for parameterized quantum operations
-   Implemented using PennyLane

### Output Layer

-   Fully connected classification layer
-   LogSoftmax activation for prediction

------------------------------------------------------------------------

## Dataset

Dataset structure:

dataset/ ├── yes/ └── no/

The dataset contains MRI brain images categorized as tumor and non-tumor
cases. Images are resized to 224×224, converted to grayscale, and
normalized before training.

Dataset Source: Public Brain MRI dataset available on Kaggle.

------------------------------------------------------------------------

## Training Configuration

-   Optimizer: Adam
-   Loss Function: Negative Log Likelihood (NLLLoss)
-   Learning Rate Scheduler: ReduceLROnPlateau
-   Train/Test Split: 80/20
-   Batch Size: 16
-   Epochs: 50

------------------------------------------------------------------------

## Evaluation

Model performance is evaluated on a held-out test split of the dataset.
Evaluation metrics include precision, recall, F1-score, and overall
accuracy.

Observed test accuracy is approximately 99%, depending on dataset split
and training initialization.

------------------------------------------------------------------------

## Running the Project

### Train the Model

python train_qcnn.py

### Run Prediction

python predict_qcnn.py

The prediction interface allows uploading MRI images and returns tumor
classification along with confidence scores and Grad-CAM based
visualization.

------------------------------------------------------------------------

## Technologies Used

-   Python
-   PyTorch
-   Torchvision
-   PennyLane
-   NumPy
-   OpenCV
-   Gradio


------------------------------------------------------------------------

## Project Context

This repository demonstrates an implementation of hybrid quantum neural
networks for medical image classification and serves as an academic
exploration of quantum machine learning techniques applied to healthcare
data.
