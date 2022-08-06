# Wildlife image classification
One of the best tools we have to study wildlife populations is camera traps. camera traps are one of the best tools available to study and monitor wildlife populations, and the enormous amounts of data they provide can be used to track different species for conservation efforts—once they are processed.

**PROBLEM STATEMENT**

Our goal is to classify the species that appear in camera trap images collected by research partners at the Wild Chimpanzee Foundation and the Max Planck Institute for Evolutionary Anthropology.

**DATA DESCRIPTION**

For this challenge, you are provided with images, along with a few attributes of each image that might be helpful in setting up your training and testing sets. The images for the training and testing sets are in train_features and test_features respectively, and additional information about each image is in train_features.csv and test_features.csv.

Each record in the dataset corresponds to a single image captured by a camera trap. Each record has one .jpg file associated with it in either the train_features or test_features directory, depending on which dataset it is a part of. Each image is accompanied by additional information in train_features.csv and test_features.csv, which contain the following fields:

1.id (string, unique identifier) - a unique identifier for each image

2.filepath (string, feature) - image path including its split directory (train or test)

3.site (string, feature) - the site in which the image was taken

There are seven types of critters captured in this set of images: birds, civets, duikers, hogs, leopards, other monkeys, and rodents. There are also images that contain no animals. Your job is to build a model that can help researchers predict whether an image contains one of these seven types of species.
