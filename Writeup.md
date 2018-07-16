# **Traffic Sign Recognition** 

The goals / steps of this project are the following:
* Load the data set (see below for links to the project data set)
* Explore, summarize and visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Analyze the softmax probabilities of the new images
* Summarize the results with a written report


[//]: # (Image References)

[image1]: ./md_images/training.png "Training Images"
[image2]: ./md_images/test.png "German Traffic Signs"
[image3]: ./md_images/speed_limit.png "Speed Limit"
[image4]: ./md_images/priority_road.png "Priority Road"
[image5]: ./md_images/turn_right.png "Turn Right Ahead"
[image6]: ./md_images/stop.png "Stop"
[image7]: ./md_images/yield.png "Yield"


### Data Set Summary & Exploration
Pandas library is used to calculate the summary statistics of the traffic signs data set:
* Size of training set is 34,799
* Size of test set is 12,630
* Shape of a traffic sign image is 32x32x3
* Number of unique classes/labels is 43

Random samples of 12 images from the training data set are plotted for visualization of the training data set. 
Example:

![alt text][image1]


### Design and Test a Model Architecture

Pre-processing of image data are performed in 2 steps:
1.	Convert from RGB to grayscale
2.	Normalize the image to equal variance: -0.5 to +0.5

The model architecture consists of the following layers:

| Layer | Description |
| - | - |
| Input | 32x32x1 Grayscale image |
| Convolution 7x7 | 1x1 stride, outputs 26x26x100 |
| RELU | Activation function |
| Max pooling | 2x2 stride, outputs 13x13x100 |
| Convolution 4x4 | 1x1 stride, outputs 10x10x150 |
| RELU | Activation function |
| Max pooling | 2x2 stride, outputs 5x5x150 |
| Dropout | 0.5 probability |
| Fully connected | Outputs 200 |
| Fully connected | Outputs 43 |

The model was adapted from LeNet-5 architecture with 2 convolutional layers  and 2 fully-connected layers, with decreasing filter size (ref. Traffic Sign Recognition with Multi-Scale Convolutional Networks). 

Using 20 epochs and batch size of 128 to train the model, the final results were:
* Accuracy of validation set is 0.957
* Accuracy of test set is 0.944

### Test a Model on New Images

Here are 8 German traffic signs found on the Internet used to test the model:

![alt text][image2] 

All images are correctly classified, giving an accuracy of 100%.

Below is the top 5 softmax probabilities:

* Speed Limit (30km/h)

![alt text][image3] 

* Priority Road

![alt text][image4] 

* Turn Right Ahead

![alt text][image5]

* Stop

![alt text][image6]

* Yield

![alt text][image7]