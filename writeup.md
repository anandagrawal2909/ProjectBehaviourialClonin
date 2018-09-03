**Behavioral Cloning Project**

---

The goals / steps of this project are the following:
* Use the simulator to collect data of good driving behavior
* Build, a convolution neural network in Keras that predicts steering angles from images
* Train and validate the model with a training and validation set
* Test that the model successfully drives around track one without leaving the road
* Summarize the results with a written report

---
## Rubric Points
Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/432/view) individually and describe how I addressed each point in my implementation.  

### Required Files
My project includes the following files:
* model.py containing the script to create and train the model
* drive.py for driving the car in autonomous mode
* model.h5 containing a trained convolution neural network 
* writeup_report.md or writeup_report.pdf summarizing the results
* run1.mp4

### Code Quality
#### Is the code functional?
* Code has been written in model.py and it is able to generate correct model and working well.
```sh
python drive.py model.h5
```
* Demo Video is on below link
[![](https://github.com/anandagrawal2909/ProjectBehaviourialClonin/blob/master/Thmbnail.jpg)](https://youtu.be/NHY75xQT0k4)


#### Is the code usable and readable?
* Yes, code has been modularised and have used relevant variable names.
* have also stored code inside an json to make more readble and re-usable

### Model Architecture and Training Strategy

#### Has an appropriate model architecture been employed for the task?
* Used CNN based network.
* Used lamba for Norrmalizarion
* Used RELU activations.
* Used fiter sizes of 5x5 and 3x3 both.

#### Has an attempt been made to reduce overfitting of the model?
* Dropouts are used to reduce overfitting.
* Model is trained on sample training data provided by CarND projec

#### Have the model parameters been tuned appropriately?
* Used Adam Optimizer to tune parameters. No manual tunning done.

#### Is the training data chosen appropriately?
* Training data was used which is given inside the course.
* Own training data was created but not used since it was not yielding good results.


### Architecture and Training Documentation

#### Is the solution design documented?
* My moel os nased on Designed used Keras libraries and CNN network.
* My moel os based on Nvidia's Model from https://arxiv.org/pdf/1604.07316v1.pd
* Input shape is 160, 320, 3
* Normalizarion Formula used = (x / 127.5) - 1.
* Cropped image from Top=74 pixels, bottom =24
* CNN_Layer1 :: Filters =24, Filter_row = 5, Filter_column =5 ,stride = (2,2), activation=RELU
* CNN_Layer2 :: Filters =36, Filter_row = 5, Filter_column =5 ,stride = (2,2), activation=RELU
* CNN_Layer3 :: Filters =48, Filter_row = 5, Filter_column =5 ,stride = (2,2), activation=RELU
* CNN_Layer4 :: Filters =64, Filter_row = 3, Filter_column =3 ,stride = (1,1), activation=RELU
* CNN_Layer5 :: Filters =64, Filter_row = 3, Filter_column =3 ,stride = (1,1), activation=RELU
* Layer6 = Flatten and dropout by 50% to avoid overfitting.
* Layer 7 = Dense 100
* Layer 8 = Dense 10
* Layer 9 = Dense 50
* Layer 10 = Dense 1 (output)
* Find loss = 'mse' and apply optimizer='adam'

#### Is the model architecture documented?
* Architecture Documeneted Above
* Batch size: 128
* Epochs: 5

#### Is the creation of the training dataset and training process documented?
* Data set was used which was provided in resources.
* Training was done using Nvidia model architecture.

### Simulation
#### Is the car able to navigate correctly on test data?
Yes, Car is able to navigate without any slippages over road boundary.
