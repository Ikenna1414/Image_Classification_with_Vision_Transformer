# Vision Transformer for Image Classification (MNIST)

This project demonstrates how to fine-tune a pretrained Vision Transformer (ViT) for image classification using PyTorch and Hugging Face Transformers. The model is trained and evaluated on the MNIST handwritten digit dataset and achieves ~99.6% test accuracy.

The project implements an end-to-end deep learning workflow including preprocessing, transfer learning, training, evaluation, and inference.

---

## Project Overview

Vision Transformers (ViTs) apply the Transformer architecture to image data by splitting images into patches and learning relationships between them using self-attention.

In this project:

- A pretrained ViT model is loaded from Hugging Face
- MNIST images are resized and converted to 3 channels
- The model is fine-tuned for 10-class digit classification
- Performance is evaluated using accuracy and a confusion matrix
- The trained model is saved and used for inference

---

## Model Architecture

Pretrained model used:

`google/vit-base-patch16-224-in21k`

Key details:

- Architecture: Vision Transformer (ViT)
- Patch size: 16×16
- Input size: 224×224
- Pretraining dataset: ImageNet-21k
- Framework: PyTorch + Hugging Face Transformers

The classification head is reinitialized for 10 MNIST classes.

---

## Dataset

Dataset used:

**MNIST Handwritten Digits**

Dataset properties:

- 60,000 training images
- 10,000 test images
- Image size: 28×28
- Classes: digits 0–9

Preprocessing steps:

- Resize images to 224×224
- Convert grayscale images to 3 channels
- Convert to tensors
- Apply random rotation augmentation

---

## Training Configuration

Training was performed using the Hugging Face Trainer API.

| Parameter | Value |
|----------|------|
| Epochs | 3 |
| Learning Rate | 2e-5 |
| Batch Size | 32 |
| Weight Decay | 0.01 |
| Optimizer | AdamW |

---

## Results

**Test Accuracy:** ~99.63%

The model performs very well across all digit classes with minimal misclassification.

### Confusion Matrix

The confusion matrix shows near-perfect classification across all digits.

---

## Example Prediction

Example inference output:

`Index 0 | true=7 | pred=7 | confidence=0.9988`

The trained model outputs both the predicted class and prediction confidence.

---

---

## Key Features

- Vision Transformer fine-tuning
- Transfer learning for image classification
- Hugging Face Trainer API
- PyTorch training pipeline
- Model evaluation and metrics
- Confusion matrix visualization
- Model saving and inference

---

## Installation

Clone the repository:
git clone https://github.com/yourusername/vision-transformer-mnist.git
cd vision-transformer-mnist


Install dependencies:
pip install torch torchvision transformers datasets scikit-learn matplotlib


---

## Running the Project

Open the notebook and run all cells:
Vision_Transformer_for_image_classification.ipynb


This will:

1. Load the MNIST dataset  
2. Preprocess images  
3. Fine-tune the ViT model  
4. Evaluate performance  
5. Generate a confusion matrix  
6. Save the trained model  

---

## Future Improvements

Potential extensions:

- Train on CIFAR-10 or CIFAR-100
- Compare CNN vs Vision Transformer performance
- Experiment with larger ViT models
- Add hyperparameter tuning
- Deploy the model as an API or web demo

---

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- Scikit-Learn
- Matplotlib
- Google Colab
