## Project 2: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Overview
---
In this project, you will use what you've learned about deep neural networks and convolutional neural networks to classify traffic signs. You will train and validate a model so it can classify traffic sign images using the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). After the model is trained, you will then try out your model on images of German traffic signs that you find on the web.

To meet specifications, the project will require submitting three files: 
* the Ipython notebook with the code
* the code exported as an html file
* a writeup report either as a markdown or pdf file  

Report of The Project
---
* Data Set Summary & Exploration

  (1) The size of training set is 34799.
  
  (2) The size of the validation set is 4410.
  
  (3) The size of test set is 12630.
  
  (4) The shape of a traffic sign image is 32 X 32 X 3 (RGB).
  
  (5) The number of unique classes/labels in the data set is 43.
  
* Preprocessing
  Four preprocessing techniques are implemented and tested: 
  
  (1) converting to grayscale; 
  
  (2) cropping the edge of image; 
  
  (3) normalize data, (pixel - 128) / 128 is used here; 
  
  (4) augmenting the brightness of image. First three procedures could significantly improve the model performance, while the last one is not. 
* Model Architecture
  LeNet is used in this project, so please refer LeNet Afchitecture (http://yann.lecun.com/exdb/publis/pdf/lecun-98.pdf)
  y final model consisted of the following layers:

| Layer         		|     Description	        					| 
|:---------------------:|:---------------------------------------------:| 
| Input         		| 32x32x3 RGB image   							| 
| Convolution 3x3     	| 1x1 stride, same padding, outputs 32x32x64 	|
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 16x16x64 				|
| Convolution 3x3	    | etc.      									|
| Fully connected		| etc.        									|
| Softmax				| etc.        									|
|						|												|
|						|												|
 
* Model Training

  (1) Batch size: since I am using my personal laptop, I decrease the batch size to 32.
  
  (2) Learning rate: 0.001, 0.005, and 0,01 are tested, and 0.001 is best.
  
  (3) Epochs: 10, 20, 30, and 40 are examined, and 30 is selected.
  
  (4) The range of cropped: 3, 4, and 5 pixels from each edge are tested, and cropping 4 pixels shows the best performance.
  
  (5) Brightness augmenting: different levels of brightness augmenting are tested, but none of them shows significant improvement.
* Solution Approach
  This trained model via using parameter-setting mentioned above gets 0.941 accuracy on validation data and 0.920 accuracy on testing data.
* Use the model to make predictions on 6 new images, please refer to the ipynb or its html file those images.
  The prediction accuracy is 1.00.
* Analyze the softmax probabilities of the new images

  (1) The characteristic of these images that might make it particularly easy/difficult for the classifier to classify them.
  
  The overall quality of thoes selected images is good, which I think it is the major reason why this model performed well when testing those images. For instance, the size of trafic symbol in each image just fits the model, and all imgaes are clear and in fine exposure time. There is no doubt that the model's performance would become wrose when testing some low quality or unusual images.
  
  (2) Accuracy comparison
  
  The model perform better when testing selected 6 images than that of testing set (1 vs 0.915). One out of reasons could be the quality of image, which is discussed above.The other reason could be the number of images downloaded from internet is very small (6 vs 12630). Therefore, the performance of test data set can be more comprehensive and realiable.  
  
  (3) How certain or uncertain the model is of its predictions
  
  From the top 5 probabilities we can find that all the first ones in all 6 groups show much higher value than the others, which indicates that the model is pretty certain for its predictions. For instance, the top 5 probabilities of img1 are as follow: 1.00000000e+00, 1.11750893e-17, 6.02813607e-27, 9.32151298e-33, and 2.16458790e-34.
  
* Potential Further Improvements
  Besides tuning the model architecture, there is one more option we could try to further improve the model performance given more time. That is to increase the mount of training data, especially for those classes with much fewer number of data than other classes.  
  



