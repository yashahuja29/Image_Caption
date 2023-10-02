# RetroFuturistic Image Caption
Although Model is not hypertuned for Retrofuturistic Images
## By Yash Ahuja
## Introduction
A pretrained Image captioning model VGG16 is trained more in Flickr8k Dataset which is a data set of 8k images and about 40k captions.
## Model
The image captioning model consists of two main components: an encoder and a decoder. The encoder is a VGG16 model without the last layer. The decoder is an LSTM RNN.
## Preprocessing and Cleaning of data
preprocessing is done using 

'''from tensorflow.keras.applications.vgg16 import VGG16, preprocess_input'''

## cleaning
The function cleans and formats each caption by performing the following operations:

Convert the caption to lowercase.
Remove digits, special characters, and non-alphabetical characters.
Remove additional spaces.
Add start ('startseq') and end ('endseq') tags to the caption.

## Tokenize Text for Image Captioning

When building an image captioning model, it's essential to preprocess and tokenize the textual data (captions) to prepare it for training. Tokenization involves converting words into numerical representations, which can be fed into the neural network. In this section, we'll discuss how to tokenize text using the Keras Tokenizer class.

## Training
The model is trained using the cross-entropy loss function. The model is trained to minimize the loss between the predicted captions and the ground truth captions.

To address the issue of variable caption size, all captions are padded to the same length, and any captions that are longer than the maximum length are truncated. This approach is easy to implement, but it can lead to a loss of information in longer captions.
## Accuracy
The BLEU-1 came out to be  0.542572 and BLEU-2 came out to be 0.315058, and anything above 0.5 is considered good and for better performance , number of epochs can be increased.

# Inference
To generate a caption for a given image, the model is first used to extract image features from the image. The image features are then passed to the decoder, which generates a caption one word at a time.
