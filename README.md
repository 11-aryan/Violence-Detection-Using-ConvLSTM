# Violence-Detection-Using-ConvLSTM
This project proposes a Deep Neural Network based method to recognize the violence in videos. **CNN** is used to extract the features from frame level in videos. Then these features are accumulated using a variant of **LSTM** that uses convolutional gates. The combination of CNN and LSTM can take the localized features that enable *local motion analysis* taking place in the videos.

### Requirements:
```
tensorflow 2.0 
numpy 1.19.5
opencv 3.4.2
keras
scikit-image
os
PIL
time
```

### Overview
This project uses an end-to-end trainable deep neural network model for classifying videos in to violent and non-violent ones. The block diagram of the proposed model is illustrated in figure. The network consists of a series of convolutional layers followed by max pooling operations for extracting discriminant features and *convolutional long short memory* (convLSTM) for encoding the frame level changes that characterizes violent scenes, existing in the video.

The code to train the model can be found in the ***Violence_Detection.ipynb*** notebook, and the code for testing videos can be found in ***Test_Video.ipynb*** notebook

<img width="" height="200" alt="2021-03-13 (2)" src="https://user-images.githubusercontent.com/55359898/111031759-20969180-842f-11eb-83e8-71bd67bcda05.png">

### Video Preprocessing for Training
20 frames are extracted from the video and fed to the VGG16 pretrained model to extract the *spatial features* from the video.

### VGG16 Pretrained model
The **VGG16** model contains a convolutional part and a fully-connected (or dense) part which is used for classification. Here the whole model is used for training, but the last layer of the model which is a fully connected layer used for classification is not  used, insted the transfer values are saved before the last layer

### Caching the transfer values
The images take a long time to get processed with the VGG16 model, by caching the transfer values, a lot of time can be saved.

### Classification
When all the videos have been processed through the VGG16 model and the resulting transfer-values saved to a cache file, then we can use those transfer-values as the input to LSTM neural network. We will then train the second neural network using the classes from the violence dataset (Violence, No-Violence), so the network learns how to classify images based on the transfer-values from the VGG16 model.


## References

	Learning to Detect Violent Videos using Convolutional Long Short-Term Memory - Swathikiran Sudhakaran and Oswald Lanz, University of Trento.

	A Review on State-of-the-Art Violence Detection Techniques – IEEE https://ieeexplore.ieee.org/abstract/document/8782115

