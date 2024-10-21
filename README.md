# Dog vs Cat Image Classification

This project is a **binary image classification** task where the model is trained to classify images as either a **dog** or a **cat**.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Installation](#installation)
- [Training](#training)
- [Evaluation](#evaluation)
- [Results](#results)
- [Usage](#usage)
- [License](#license)

## Introduction
The goal of this project is to develop a convolutional neural network (CNN) to classify images of dogs and cats. This is a common deep learning task, especially useful for beginners to learn how to work with image data and neural networks.

## Dataset
The dataset used consists of labeled images of dogs and cats. Each image is categorized as either:
- `0`: **Cat**
- `1`: **Dog**

### Data Preprocessing
- The images are resized to `(64, 64, 3)` to standardize the input size for the model.
- Labels are encoded as binary (`0` for cat, `1` for dog).

## Model Architecture
We used a simple **Convolutional Neural Network (CNN)** with the following layers:
- **Convolutional Layers**: Extract features from the images.
- **MaxPooling Layers**: Downsample the image to reduce complexity.
- **Fully Connected Layer**: Classify the image as either a dog or a cat.
- **Dropout Layer**: Regularization to prevent overfitting.
- **Output Layer**: Sigmoid activation for binary classification.

Here is the model summary:

```plaintext
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d (Conv2D)              (None, 62, 62, 32)        896       
_________________________________________________________________
max_pooling2d (MaxPooling2D) (None, 31, 31, 32)        0         
_________________________________________________________________
conv2d_1 (Conv2D)            (None, 29, 29, 64)        18496     
_________________________________________________________________
max_pooling2d_1 (MaxPooling2D) (None, 14, 14, 64)      0         
_________________________________________________________________
flatten (Flatten)            (None, 12544)             0         
_________________________________________________________________
dense (Dense)                (None, 128)               1605760   
_________________________________________________________________
dropout (Dropout)            (None, 128)               0         
_________________________________________________________________
dense_1 (Dense)              (None, 1)                 129       
=================================================================
Total params: 1,624,281
Trainable params: 1,624,281
Non-trainable params: 0
