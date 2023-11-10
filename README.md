# BreaKHis-Classification-with-CBAM-Block

CBAM or Convolutional Block Attention Module is an attention module combining channel attention and spatial attention. Combining the both can make so that the model focuses on the most relevant parts of the input images.

In this colab file we have used the benchmark BreaKHis dataset consisting of benign and malignant images of breast cancer. The histopathology stains in all the images are first normalized by using Adaptive Histogra Equalization to brighten and Gaussian Filter to lessen the noise. The channel and spatial attention blocks are then applied to the pretrained EfficientNetV2S model getting an incredible accuracy of 92%.
