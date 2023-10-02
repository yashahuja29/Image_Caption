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
```

Data cleaning is carried out through a function that performs the following operations on each caption:

Converts the caption to lowercase.
Removes digits, special characters, and non-alphabetical characters.
Removes extra spaces.
Adds start ('startseq') and end ('endseq') tags to the caption.

## Tokenize Text for Image Captioning

In order to prepare textual data (captions) for training, it is essential to tokenize it. Tokenization involves converting words into numerical representations, which can then be fed into the neural network. Below, we'll explain how to tokenize text using the Keras Tokenizer class.

## Training
 he model is trained using the cross-entropy loss function. The objective is to minimize the loss between the predicted captions and the ground truth captions.

To address the challenge of variable caption sizes, all captions are padded to the same length, and any captions exceeding the maximum length are truncated. While this approach is easy to implement, it may result in a loss of information in longer captions.

## Accuracy
The evaluation of the model yields a BLEU-1 score of 0.542572 and a BLEU-2 score of 0.315058. Generally, scores above 0.5 are considered good, and for enhanced performance, increasing the number of training epochs can be explored.

## Inference

To generate a caption for a given image, the model follows these steps:

1. Extracts image features from the input image using the encoder.
2. Passes these features to the decoder, which generates a caption one word at a time.
