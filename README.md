# Flower Classification using ResNet-50

## Overview

This project, part of the fellowship.ai application process, uses a pre-trained ResNet-50 model to classify images from the 102 Category Flower Dataset.

## Project Workflow

### 1. Dataset Preparation

- **Data Extraction**: Extracted images from the 102flowers.tgz archive.
- **Label Loading**: Loaded image labels from imagelabels.mat file.
- **Data Organization**: Created a structured DataFrame containing file paths and corresponding labels.
- **Data Splitting**: Divided the dataset into training and validation sets, ensuring a balanced distribution of classes.

### 2. Data Augmentation

- **Training Data Augmentation**: Used the `ImageDataGenerator` for real-time data augmentation, applying transformations such as rotation, width and height shifts, shearing, zooming, and horizontal flipping.
- **Validation Data Preparation**: Rescaled validation images to normalize pixel values within the [0, 1] range.

### 3. Model Architecture

- **Base Model**: Used the ResNet-50 architecture, pre-trained on the ImageNet dataset, excluding the top classification layer.
- **Fine-Tuning**: Unfroze the last 10 layers of the ResNet-50 model to allow fine-tuning on the flower dataset.
- **Custom Layers**: Added a global average pooling layer, a dropout layer to prevent overfitting and a dense layer with a softmax activation function for multi-class classification.

### 4. Model Training

- **Compilation**: Compiled the model using the Adam optimizer with a reduced learning rate to help fine-tuning.
- **Training Process**: Trained the model for 32 epochs, using training and validation data to monitor and improve the model's performance.

### 5. Performance Evaluation

- **Validation Accuracy**: Achieved a high validation accuracy, showing the model’s ability to classify the flower images correctly.
- **Model Evaluation**: Evaluated the final model on the validation set, resulting in a notable validation accuracy of 97.37%.
- **Result Visualization**: The training and validation accuracy graph shows a steady improvement over epochs, indicating effective learning and generalization by the model.

![download](https://github.com/user-attachments/assets/3b9023ec-5e3e-41be-b7d8-a1951caef9cf)

### 6. Results Visualization

- **Accuracy Plots**: Generated plots of training and validation accuracy across epochs to visualize the model’s learning progress and performance improvements.

## Conclusion

This project successfully applied transfer learning with ResNet-50 to classify flower images accurately. Combining data augmentation and fine-tuning helped achieve an effective classification model.
