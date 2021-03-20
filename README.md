# CNN_Dog_Breed
### by Iván Lucas López

[//]: # (Image References)

[image1]: ./images/boxer_example.JPG "Sample Output"

### Table of Contents

1. [Installation](#installation)
2. [Project Overview](#motivation)
3. [Project Instructions](#files)
4. [Strategy to solve the problem](#Strategy)
5. [Metrics](#Metrics)
6. [EDA and Models](#model)
7. [Results](#results)
8. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

There should be no necessary libraries to run the code here beyond the Anaconda distribution of Python.  
The code should run with no issues using Python versions 3.*.


List of libraries used:
- from sklearn.datasets import load_files       
- from keras.utils import np_utils
- import numpy as np
- from glob import glob
- from keras.callbacks import ModelCheckpoint
- import random
- import cv2
- import matplotlib.pyplot as plt  
- from keras.applications.resnet50 import ResNet50
- from keras.preprocessing import image 
- from tqdm import tqdm
- from keras.applications.resnet50 import preprocess_input, decode_predictions
- from PIL import ImageFile  
- from keras.layers import Conv2D, MaxPooling2D, GlobalAveragePooling2D
- from keras.layers import Dropout, Flatten, Dense
- from keras.models import Sequential
- from keras.callbacks import ModelCheckpoint
- from extract_bottleneck_features import *


## Project Overview <a name="motivation"></a>

This project uses Convolutional Neural Networks (CNNs). 
In this project, I have learned how to build a pipeline to process real-world, user-supplied images. 

Given an image of a dog, the algorithm will identify an estimate of the canine’s breed. 

If supplied an image of a human, the code will identify the resembling dog breed.

Here is an example!

![Sample Output][image1]


## Project Instructions <a name="files"></a>

### Instructions to run this proyect

1. Clone the repository and navigate to the downloaded folder.
```	
git clone https://github.com/LLI-hub/CNN_Dog_Breed.git
cd dog-project
```

2. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/dogImages`. 

3. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/lfw`.  If you are using a Windows machine, you are encouraged to use [7zip](http://www.7-zip.org/) to extract the folder. 

4. Download the [VGG-16 bottleneck features](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG16Data.npz) for the dog dataset.  Place it in the repo, at location `path/to/dog-project/bottleneck_features`.

5. Open the notebook.
```
jupyter notebook dog_app.ipynb
```

## Strategy to solve the problem <a name="Strategy"></a>

The Latin phrase “Divide et impera” is attributed to Julius Cesar and is the strategy followed in this proyect.

The idea is create a single output that tell us:
- If there are a human in the image.
- If there are a dog in the image.
- The dog breed.

So I have used 3 different models:
- A model to identify if there is a human face in the image.
- A model to identify if there is a dog in the image.
- A model to identify the dog breed.

## Metrics <a name="Metrics"></a>
All the models are evaluated using the accuracy.
On the human model the accuracy will be: (times a human is detected in an image where there is a human/ total images showing a human used to test the model).
On the dog model the accuracy will be: (times a dog is detected in an image where there is a dog/ total images showing a dog used to test the model).
On the dog breed model: Times the breed is correctly assigned / Number of images used to test the model.

## EDA and Models <a name="model"></a>
Jupyter notebook named dog_app.ipynb

## Results<a name="results"></a>

The main findings of the code can be found at the post available [here](https://i-lucas.medium.com/you-look-like-my-best-friend-90edbfa581c8).

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to Udacity for the data and the base Jupyter File.  
You can find the Licensing for the data and other descriptive information at the link available [here](https://github.com/udacity/dog-project).
