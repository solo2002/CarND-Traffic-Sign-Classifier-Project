## Project 2: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Overview
---
In this project, you will use what you've learned about deep neural networks and convolutional neural networks to classify traffic signs. You will train and validate a model so it can classify traffic sign images using the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). After the model is trained, you will then try out your model on images of German traffic signs that you find on the web.

To meet specifications, the project will require submitting three files: 
* the Ipython notebook with the code
* the code exported as an html file
* a writeup report either as a markdown or pdf file  

Summary of The Project
---
* Preprocessing
  Four preprocessing techniques are implemented and tested: 
  
  (1) converting to grayscale; 
  
  (2) cropping the edge of image; 
  
  (3) normalize data, (pixel - 128) / 128 is used here; 
  
  (4) augmenting the brightness of image. First three procedures could significantly improve the model performance, while the last one is not. 
* Model Architecture
  LeNet is used in this project, so please refer LeNet Afchitecture (http://yann.lecun.com/exdb/publis/pdf/lecun-98.pdf)
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
  I have a little problem with softmax probabilities. Either 0. or 1. is printed when softmax(logits) is called. If without using softmax function, the numbers without converting to probabilites are shown.
* Potential Further Improvements
  Besides tuning the model architecture, there is one more option we could try to further improve the model performance given more time. That is to increase the mount of training data, especially for those classes with much fewer number of data than other classes.  
  



