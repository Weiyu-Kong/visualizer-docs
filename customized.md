---
title: Customized
nav_order: 2
---

## Getting Your Own Training Dynamics and Visualize It

### Prerequisites
Assume the root directory of the training process is `content_path`. The following data needs to be saved before training the visualizer model (i.e., the visualizer model is not responsible for generating these):
1. Subject model: The target model, saved in content_path/model/(epoch).pth. For example, the model directory contains target models for different epochs: 1.pth, 2.pth, 3.pth, etc.

2. Representation: High-dimensional features of the samples, saved in content_path/dataset/representation/(epoch).npy. The dataset/representation directory contains high-dimensional features for different epochs: 1.npy, 2.npy, 3.npy, etc. The shape of the numpy array in each file is [number of samples, feature dimensions].

3. Prediction: The raw output of the samples from the original model, saved in content_path/dataset/prediction/(epoch).npy. The shape of the numpy array in each file is [number of samples, number of classes], representing the output of each sample on the original model. For example, if there are ten classes, each sample will have 10 scores.

4. Label: The correct labels for each sample, saved in content_path/dataset/label/labels.npy. This is the numpy form of all sample labels in the dataset, with the shape of the numpy array being [number of samples] (a list of numbers).

5. Index: (Optional) If training and testing data need to be split, create an index.json file and save it in content_path/index.json.

6. Config: Configuration file, automatically generated or manually filled, saved in content_path/config.json.

7. model.py: The original model definition file, saved in content_path/model.py.

### Training the Visualizer Model
