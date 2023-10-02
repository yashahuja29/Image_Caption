# Retrofuturistic Image Captioning

**By Yash Ahuja**

## Introduction

This project showcases a pretrained image captioning model based on VGG16, primarily trained on the Flickr8k Dataset. Flickr8k consists of 8,000 images with approximately 40,000 associated captions.

## Model

The image captioning model comprises two main components: an encoder and a decoder. The encoder uses a VGG16 model (excluding the last layer), while the decoder employs an LSTM RNN.

## Preprocessing and Data Cleaning

**Preprocessing** is accomplished using:

```python
from tensorflow.keras.applications.vgg16 import VGG16, preprocess_input
