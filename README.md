# Flower-Species-Classifier
It was the final project for the Pytorch Challenge held by Udacity in collaboration with Facebook.

## Image Classifier
Going forward, AI algorithms will be incorporated into more and more everyday applications. For example, you might want to include an image classifier in a smartphone app. To do this, you'd use a deep learning model trained on hundreds of thousands of images as part of the overall application architecture. A large part of software development in the future will be using these types of models as common parts of applications.

In this project, you'll train an image classifier to recognize different species of flowers. You can imagine using something like this in a phone app that tells you the name of the flower your camera is looking at. In practice, you'd train this classifier, then export it for use in your application. We'll be using this dataset of 102 flower categories.

When you've completed this project, you'll have an application that can be trained on any set of labelled images. Here your network will be learning about flowers and end up as a command line application. But, what you do with your new skills depends on your imagination and effort in building a dataset.

## The Dataset
The data set contains images of flowers from 102 different species. We've provided a training set and a validation set. 
You can [download the images from here](https://s3.amazonaws.com/content.udacity-data.com/courses/nd188/flower_data.zip) as a zipped archive. Just uncompress it and you should be good to go.

## Results
I used a pretrained model, **densenet201**, to classify 102 different types of flowers. First I froze features and trained the newly defined classifier and got an accuracy of about **96%**.
Then I unfroze the entire model and trained further to increase the accuracy to more than **98%**.
* Criterion - **nn.NLLLoss()**
* Optimizer - 
    1. _For freezed model_: **optim.Adam(model.classifier.parameters(), lr=0.001)**
    2. _For unfreezed model_: **optim.Adagrad(model.parameters(), lr=0.0001)**
* Schedular - **optim.lr_scheduler.ReduceLROnPlateau(optimizer,'min')**
