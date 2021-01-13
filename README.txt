Traffic Sign Recognition using modified LeNet(CNN) (provided in both format (Colab notebook and .py))

1. Description 

The project is a traffic sign recognition problem where GTSRB dataset is used to train the model. The model architecture is LeNet 
which is then modified, accordingly.

Link to the database: https://bitbucket.org/jadslim/german-traffic-signs

#Prerequisites:
Python 3.5
OpenCV2
Keras

2. PRE_PROCESSING FUNCTIONS

The detection phase makes use of image processing techniques like gray scale conversion, histogram equalization and normalzation. 
This can be found in functions:

def grayscale
def equalize

3. IMPROVEMENTS
The improvements which are made through the entire process of fine tuning the model involve following:

improv #1: Fine Tuning Model by changing the learn rate of the Adam optimizer, too high learning rate affects the accuracy (from lr=0.01 to lr=0.001)
improv #2: Increasing number of filters
improv #3: Adding more convolutional layers
improv #4: Adding dropout layers

These improvements are mentioned in section #leNet implementation where def leNetmodified_model() is defined 

4. ImageDataGenerator

To increase the number of training images for the model to learn more and more features, data augmentation method is used.
These methods are as follows:
i.	 Rotating 
ii.	Shifting: Height, Width
iii.	Zooming
iv.	Shear range
For this Keras API ImageDataGenerator is used.

5. Use of model.fit_generator
Use of ImageDataGenerator leads to use model.fit_generator instead of model.fit, hence modifications are made. The steps_per_epoch parameter 
is important which is given by 	number of training examples/batch_size (=>34799/50 = 695 ) This parameter can change batch size and thus adjusted 
by keeping an eye on the accuracy.

6. Total number of epochs are 15

7. Ultimately loss and accuracy are plotted for observations and test score is printed which gives overall test accuracy. 

8. TESTING
In testing part, the images from internet sources are fed into the model.
Following links can be tried for testing this code: 

https://c8.alamy.com/comp/J2MRAJ/german-road-sign-bicycles-crossing-J2MRAJ.jpg
https://c8.alamy.com/comp/J2MRAJ/german-road-sign-bicycles-crossing-J2MRAJ.jpg\
https://c8.alamy.com/comp/G667W0/road-sign-speed-limit-30-kmh-zone-passau-bavaria-germany-G667W0.jpg






