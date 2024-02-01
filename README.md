# BreaKHis-Classification-with-CBAM-Block

## Dataset
For this project, the benchmark BreaKHis dataset consisting of 7909 images of histopathological breast tissue in two categories namely benign and malignant is used. The benign category consists of 2480 images and the malignant 5429. 

## Preprocessing
To provide the model with images of uniform dimensions, all the photos of both datasets were rescaled to 224×224 pixels. The images were converted into LAB, and to increase the overall contrast, Adaptive Histogram Equalization was applied. The images were denoised using a Gaussian Filter with a kernel size of (3,3). The data was then split into a ratio of 80:10:10 for training, validation, and test, respectively. Data Augmentation was performed using the ImageDataGenerator from Keras to normalize, augment, and increase the image data, thereby addressing class imbalance. Data Augmentation can assist in increasing data size and improve the model's generalization. Each of the training, validation, and testing sets comprised of 32 batches.

## CBAM
CBAM or Convolutional Block Attention Module is an attention module combining channel attention and spatial attention. Combining the both can make so that the model focuses on the most relevant parts of the input images. This module is integrated with our EfficientNetV2S model.

## EfficientNetV2S-CBAM
Out of the EfficientNet family of models, EfficientNetV2S with ImageNet weights is chosen as our base model. The layers of the model are frozen and the output of the base model goes through the CBAM module, followed by a GAP layer as a down-sampling tool. A dropout rate of 0.6 is used to prevent the possibility of overfitting, as it randomly drops off some neurons every iteration to make sure the the model doesn't get overly influenced by a bunch of samples. A dense layer with 1024 neurons with ReLu activation and l2 regularizer, which penalizes the cost function, with a value of 0.001 is next. The output layer comprises of 1 neuron with a sigmoid activation function as it is a binary classification task.
