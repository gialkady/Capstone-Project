## Best restaurant to serve
![img](https://github.com/gialkady/ml_zoomcamp/blob/Homeworks/Capstone%20Project/images/istockphoto-531306158-612x612.jpeg)


## overview 

This project is done as part of the Machine Learning course held by Alexey Grigorev.


## Idea (Problem Description)

How many times you saw a food image on the internet and you feel that you want to eat it NOW 🤩 😉  

In this project, we tried to make your dreams come true. The idea is a web service that helps people to know the best restaurant to serve the food dish on an image on their city. 

- Firstly, the user upload the food image url.
- ML engine based on deep learning will classify the image (food class). 
- According to the class of food, the system will response with the name of the best restaurant to serve the dish in the user's city.

![img](https://github.com/gialkady/ml_zoomcamp/blob/Homeworks/Capstone%20Project/images/Best%20Restaurant%20to%20serve.png)

## Dataset

The dataset used in this project is Food-101 dataset (https://www.kaggle.com/kmader/food41)

Food-101 is a dataset consisting of 101 food classes with 1000 images per class. For each class, 250 images are reserved as for the test set and the rest 750 images for training (80% train, 20% val). In the directory food-101 we find a folder with images and one with meta information. The images folder contains 101 folders with 1000 images each. Each folder contains images of a specific food class while the meta folder contain the information tells us what the train and test (validation) images are.

**meta** folder contains the text files - train.txt and test.txt  
**train.txt** contains the list of images that belong to training set  
**test.txt** contains the list of images that belong to test set  
**classes.txt** contains the list of all classes of food

## Exploratory data analysis (EDA)
  

After downloading the dataset, i explored the folders and loaded some random images of the dataset to test the dataset problems. As a result, i recognized the following problems:

- Small amount of training data for each class
- Many classes look similar to each other (steak vs filet mignon)
- Many images in the dataset have poor lighting or framing.
- Several images contain multiple correct classes (ex burgers & fries)
- Number of mislabeled images.
- Image shapes vary within class

Most of the dataset problems can be solved through applying "Image augmentation". 

## Data preparation

Food-101 Dataset contains 101,000 images across 101 classes. The dataset is split into 75,750 training and 25,250 test images which defined by test.json and train.json. The original download has the train and test images in the same folders. Here we separate out train and test images into different directories.

train ='./food-101/meta/train.txt'

test ='./food-101/meta/test.txt'

Check EDA and Data preparation notebook ➡️ (https://github.com/gialkady/ml_zoomcamp/tree/Homeworks/Capstone%20Project)

## Models training 

Three models are trained through which we will choose the best model to use for our application which are:

- ✅ **Xception** 
- ✅ **InceptionV3** 
- ✅ **DenseNet121**

The transfer learning is applied and the convolutional layers only kept in each model.The best model is used based on the best performance of the model seen from accuracy score of the validation data for each trained model by using checkpointer to save best model.

Check Models training ➡️ (https://github.com/gialkady/ml_zoomcamp/tree/Homeworks/Capstone%20Project/Models%20Training)

## Local Deployment

Tools: mac laptop, pycharm and anaconda3

After the final model is obtained, apply the next steps:
- Convert notebook into .py file -> train.py
- Put all required files (ex. model_trained_101class.tflite)
- Make a virtual enviroment for deep learning includig (python 3.7.11, tensorflow, tflite 2.4.0, tflite-runtime 2.5.0, keras-image helper)
- Open terminal in project folder and test file without docker -> python3 train.py
- Download docker in terminal or if you mac user download "docker for mac".
- Build docker image (write all dependencies needed to run model) -> 'Docker build -t food_classification .'
- Run model in the docker container in terminal 
- Test response file

For more details ➡️ ()

## Cloud Deployment 

- Open AWS console -> lambda -> container image
- Publish container image in Amason ECR (Elastic Container Registry):
    - pip install awscli
    - create repistory in Amason ECR
    - Push Docker image to repo in AWS 
- Create function for container image in AWS
- Test model in AWS repo
- Expose the lambda function via API Gateway
- Finally, you will have a public endpoint url through which the model can be tested. 
     
For more details ➡️ ()
