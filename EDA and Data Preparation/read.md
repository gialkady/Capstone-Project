
## Exploratory data analysis (EDA)
  

After downloading the dataset, i explored the folders and loaded some random images of the dataset to test the dataset problems. As a result, i recognized the following problems:

- Small amount of training data for each class
- Many classes look similar to each other (steak vs filet mignon)
- Many images in the dataset have poor lighting or framing.
- Several images contain multiple correct classes (ex burgers & fries)
- Number of mislabeled images.
- Image shapes vary within class

Most of the dataset problems can be solved through applying "Data augmentation". It will be applied in the test time to increase the accuracy.

## Data preparation

Food-101 Dataset contains 101,000 images across 101 classes. The dataset is split into 75,750 training and 25,250 test images which defined by test.json and train.json. The original download has the train and test images in the same folders. Here we separate out train and test images into different directories.

train ='./food-101/meta/train.txt'

test ='./food-101/meta/test.txt'
