This is a short project that uses Image Clasification inference to help make an every day interaction more efficient.
The goal of training this model was to see the potential usefulness and accuracy of what hand controls could look like with a computer.
My first thought (because I always listen to music while working) was to make controlling your music an easier task. All it takes is 
a camera. Using an enhanced version of my model, a user would simply have to hold out an open hand under a camera to play their music, 
close their hand into a fist to stop it, and make an L shape with their hand to skip to the next song etc. The possibilities of hand
controlling computer are endless, but I can imaging something like how Tony Stark interacts with Jarvis in Iron Man. 

This code was all forked from the dusty-nv jetson inference project on Github (https://github.com/dusty-nv/jetson-inference)
I used some of this code and documentation to create and train my model. Follow the documentation at 
https://github.com/sbenetz/jetson-inference/blob/master/docs/pytorch-cat-dog.md  and
https://github.com/sbenetz/jetson-inference/blob/master/docs/pytorch-collect.md to see how to train and run the model. 

Where to find things:
Video demonstration of model  - Main project folder 
Porject folder with model and data for training- python/project

Steps of how to use: 
start the docker by running docker/run.sh - this should create an environment that has all the necessary packages and modules for the project. 
change directory into python/project
run "imagenet.py --model=models/hands_final/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=data/hands_final/labels.txt /dev/inputs/js0"
This should open a window with the image of your connected USB camera and will try to detect any hand signals that are being given in front of the camera.

How I got the model: 
took a data set of around 50+ images for each category and trained the model by using train.py. Then we must convert it to an onnx file so that it can be soon 


Overall my model could use a lot more training. It seems to recognize the pause hand signal a bit more than the "next" or the "play." But it does not even get close to 100% in real ratio.


This is a very expensive way of changing music, but I'd like to see the potential of where these things could go. 


Created by Shane Benetz 2021