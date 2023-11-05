# Image Segmentation of Handwritten Digits

We will build a model for predicting segmentation masks of handwritten digits. The model will be trained on the M2NIST dataset, a multi-digit MNIST dataset. The goal is to create a Convolutional Neural Network (CNN) for image segmentation. The model will be evaluated using intersection over union (IOU) and Dice Score metrics.

## Dataset
The [M2NIST](https://www.kaggle.com/farhanhubble/multimnistm2nist) is a **multi digit** [MNIST](http://yann.lecun.com/exdb/mnist/) dataset contains images of multiple MNIST digits along with corresponding segmentation masks. The dataset is available on [Kaggle](https://www.kaggle.com). The images and masks are in numpy array format, with image dimensions of 64x84 pixels.
![Data](https://github.com/hellfire95/Image-Segmentation-of-Handwritten-Digits/blob/main/hand_written_data.png?raw=true)

## Preprocessing
The dataset is available in numpy array files, making it easy to preprocess. You can make appropriate splits for training, validation, and testing as needed for your problem.

## Model Architecture
The image segmentation model consists of two paths:
1. Downsampling Path: This part extracts features from the image through convolution and pooling layers. We will create a custom CNN for this path.
2. Upsampling Path: This takes the output of the downsampling path and generates predictions while upsampling the image to its original size. We will use an FCN-8 decoder for this path.
![FCN-8](https://github.com/hellfire95/Image-Segmentation-of-Handwritten-Digits/blob/main/fcn8.png?raw=true)

## Model Evaluation
The model's performance will be evaluated using the intersection over union (IOU) and Dice Score metrics, which measure the accuracy of segmentation predictions.
![Model predictioin](https://github.com/hellfire95/Image-Segmentation-of-Handwritten-Digits/blob/main/hand_written_prediction.png?raw=true)

## Metrics
The model will be evaluated using the IOU and Dice Score metrics. These metrics provide insight into the quality of segmentation predictions.
The model will be evaluated using the following metrics:

- Intersection Over Union (IOU):
  IOU = area_of_overlap / area_of_union

- Dice Score:
  Dice Score = 2 * area_of_overlap / combined_area
The provided code includes functions for visualizing the dataset and its annotations, creating the model architecture, and compiling the model with appropriate metrics.

## Result 
![prediction result](https://github.com/hellfire95/Image-Segmentation-of-Handwritten-Digits/blob/main/hand_written_result.png?raw=true)