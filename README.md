# RetroFuturistic Image Caption
Although Model is not hypertuned for Retrofuturistic Images
## By Yash Ahuja
## Introduction
A pretrained Image captioning model VGG16 is trained more in Flickr8k Dataset which is a data set of 8k images and about 40k captions.
## Model
The image captioning model consists of two main components: an encoder and a decoder. The encoder is a VGG16 model without the last layer. The decoder is an LSTM RNN.
## Training
The model is trained using the cross-entropy loss function. The model is trained to minimize the loss between the predicted captions and the ground truth captions.

To address the issue of variable caption size, all captions are padded to the same length, and any captions that are longer than the maximum length are truncated. This approach is easy to implement, but it can lead to a loss of information in longer captions.

# Inference
To generate a caption for a given image, the model is first used to extract image features from the image. The image features are then passed to the decoder, which generates a caption one word at a time.
