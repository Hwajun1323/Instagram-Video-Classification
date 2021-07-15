# Video Classification with convLSTM neural network
## 1. Description

This is a bachelor project from university of Groningen. This project aim to classify the environment of video from Instagram. There are 5 classes of video environment. 
- [Office]
- [Restaurant]
- [Muesum]
- [Dining Room]
- [Child's Room]

## 2. Tech

Project uses a number of tech to work properly:

- [Tensorflow] 
- [Keras] 
- [Sklearn]
- [OpenCV] 

## 3. Features
This section will explain the feature of code from this project.
#### Frames Extraction
To train each video properly, we use equidistance frames per video. Equidistance frames is selecting same interval frames from the whole frames. For example, if a whole frames number of video is 100 and we want to extract 20 frames, we will extract 5, 10, 15, 20, 25, 30,..., 95, 100 frames. To implement this, the brief steps are follow:
- Get total frames number of each video
- Divide total number of frames by the number of frames we want to extract (This calls frames step)
- Extract frames at intervals of frames steps

#### Create Data
There is a 'create_data' function to make X and Y data before training. This function call 'frames_extraction' to get X with equidistance frames.

#### Create Model
After creating data, we need to make model. This project focus on convLSTM neural network and we choose 'ADAM' optimizer.
The entire model consists of layers as follows:
- convLSTM
- BatchNormalization
- MaxPooling
- Flatten
- Dense
- Dropout

#### Train with Cross Validation
To prevent overfitting, we evalute the result with cross validation. This project divide 3 part of data but this can be more than 3 but it will take much more time. 

#### Evaluate
We evaluate the reuslt of training with classification report and confusion matrix.


