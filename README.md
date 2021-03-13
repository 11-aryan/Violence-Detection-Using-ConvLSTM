# Violence-Detection-Using-ConvLSTM

## Introduction
This project proposes a Deep Neural Network based method to recognize the violence in videos. CNN is used to extract the features from frame level in videos. Then these features are accumulated using a variant of LSTM that uses convolutional gates. The combination of CNN and LSTM can take the localized features that enable local motion analysis taking place in the videos.

## Proposed Methodology
The goal is to develop an end to-end trainable deep neural network model for classifying videos in to violent and non-violent ones. The block diagram of the proposed model is illustrated in figure. The network consists of a series of convolutional layers followed by max pooling operations for extracting discriminant features and convolutional long short memory (convLSTM) for encoding the frame level changes that characterizes violent scenes, existing in the video.

<img width="806" alt="2021-03-13 (2)" src="https://user-images.githubusercontent.com/55359898/111031759-20969180-842f-11eb-83e8-71bd67bcda05.png">

The method consists of extracting a set of frames belonging to the video, sending them to a pretrained network called VGG16, obtaining the output of one of its final layers and from these outputs train another network architecture with a type of special neurons called LSTM. These neurons have memory and are able to analyze the temporal  information of the video, if at any time they detect violence, it will be classified as a violent video and the concerned authorities will be alerted to take further action.


## References

	Learning to Detect Violent Videos using Convolutional Long Short-Term Memory - Swathikiran Sudhakaran and Oswald Lanz, University of Trento.

	A Review on State-of-the-Art Violence Detection Techniques – IEEE https://ieeexplore.ieee.org/abstract/document/8782115

