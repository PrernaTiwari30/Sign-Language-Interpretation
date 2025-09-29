# Sign-Language-Interpretation
This project is a real-time Sign Language Recognition System designed to interpret hand gestures using a CNN-based model. It captures webcam input, processes the image, classifies the sign, and displays the result through a Tkinter GUI. It also includes an auto-suggest feature using Hunspell to assist with spelling correction.

# Project Overview

This system interprets hand gestures corresponding to sign language (ASL) characters. It uses:
    Convolutional Neural Networks (CNNs) for classification
    Tkinter GUI for interactive user interface
    OpenCV for real-time webcam feed
    Hunspell for spelling correction and word suggestion
# Modules and Workflow
**1. Training Data Acquisition**
     Captured hand gesture samples using webcam
     Defined Region of Interest (ROI) for consistent image framing
     Preprocessing included:
      Resizing to 128x128 pixels
      Normalization
     Organized clean datasets with multiple samples per class

2. Testing Data Acquisition
     Similar process to training data
     Captured labeled samples per class
     Ensured class balance for robust evaluation
   
3. Model Development & Evaluation
   Dataset Preprocessing
   
     Converted all images to grayscale for simplicity

     Applied Gaussian Blur to reduce noise

     Data Augmentation to improve generalization

     Resized all images to 128x128 pixels
   

   CNN Architecture

     Input Layer: 128x128 grayscale images
   

     Convolutional Layers:

      Conv2D with 32 filters, 3x3 kernel, ReLU activation

      Another Conv2D layer for deeper feature learning

     Pooling Layer: MaxPooling to reduce spatial dimensions

     Flatten Layer: Converts feature maps to 1D vector
   

     Dense Layers:

      Multiple fully connected layers with ReLU

      Dropout applied to prevent overfitting
   

     Output Layer:

      27 units (for 26 letters + background class)

      Softmax activation for multi-class classification
   

   Training

     Loss Function: categorical_crossentropy

     Optimizer: Adam

     Epochs: 5

     Validation on held-out test set

     Model saved and reloaded for evaluation

5. GUI Deployment Framework

     GUI with Tkinter for user interaction

     Real-time webcam integration using OpenCV

     Recognized signs displayed as text output

     Auto-Suggest Feature:

     Integrated using Hunspell

     Suggests top 3 words based on partially formed input

     Dynamically updates as signs are recognized

     Optimized for lightweight deployment
