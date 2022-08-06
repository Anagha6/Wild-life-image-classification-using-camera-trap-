# Wildlife image classification using camera trap images

One of the best tools we have to study wildlife populations is camera traps. camera traps are one of the best tools available to study and monitor wildlife populations, and the enormous amounts of data they provide can be used to track different species for conservation efforts—once they are processed.

## **PROBLEM STATEMENT**

Our goal is to classify the species that appear in camera trap images collected by research partners at the Wild Chimpanzee Foundation and the Max Planck Institute for Evolutionary Anthropology.

**DATA DESCRIPTION**

For this challenge, you are provided with images, along with a few attributes of each image that might be helpful in setting up your training and testing sets. The images for the training and testing sets are in train_features and test_features respectively, and additional information about each image is in train_features.csv and test_features.csv.

Each record in the dataset corresponds to a single image captured by a camera trap. Each record has one .jpg file associated with it in either the train_features or test_features directory, depending on which dataset it is a part of. Each image is accompanied by additional information in train_features.csv and test_features.csv, which contain the following fields:

1.id (string, unique identifier) - a unique identifier for each image

2.filepath (string, feature) - image path including its split directory (train or test)

3.site (string, feature) - the site in which the image was taken

There are seven types of critters captured in this set of images: birds, civets, duikers, hogs, leopards, other monkeys, and rodents. There are also images that contain no animals. Your job is to build a model that can help researchers predict whether an image contains one of these seven types of species.

**TOOLKIT**

I have created a resnet-50 model for image classification thus I have used a simple convultional neural network model architecture to train the models.ResNet-50 is a convolutional neural network that is 50 layers deep. ResNet, short for Residual Networks is a classic neural network used as a backbone for many computer vision tasks.

Model summary:

->  __init__ will instantiate the dataset object with two dataframes: an x_train df containing image IDs and image file paths,  and a y_train df containing image IDs and labels. This will run once when we first create the dataset object

->  __getitem__ will define how we access a sample from the data. This method gets called whenever we use an indexing operation like dataset[index]. In this case, whenever accessing a particular image sample ,the following will happen:
    
           1. look up the image filepath using the index
    
           2. load the image with PIL.Image
    
           3.apply some transformations 
    
           4.return a dictionary containing the image ID, the image itself as a Tensor, and a label 
    
->  __len__ simply returns the size of the dataset, which we do by calling len on the input dataframe.
Here we are also defining a set of transformations, which are defined in the __init__ and called in the __getitem__ special methods.
    
    ->transforms.Resize((224, 224)) ResNet50 was trained on images of size 224x224 so we resize to the same dimensions here.
    
    ->transforms.ToTensor() converts the image to a tensor. Since we are passing in a PIL Image at this point, PyTorch can recognize it as an RGB image and will automatically convert the input values which are in the range [0, 255] to a range of [0, 1].
    
    ->transforms.Normalize(...) normalizes the image tensors using the mean and standard deviation of ImageNet images.
    
  **INSTALLATION**
  
To run this code in your local system you have to download this repository using-
  
git clone https://github.com/Anagha6/Wildlife_Image_classification.git
  
install the required python packages using-

pip install -r requirements.txt
    
**TRAINING AND EVALUATION**

I have used my local system for training this model.

Intel(R) Core(TM) i3-1005G1 CPU @ 1.20GHz   1.19 GHz;RAM:12.0 GB

**FURTHER MODIFICATIONS:**

We can also try another pretrained model like EfficientNet, or another ResNet model with more layers like ResNet152,we may get better accuracy.

**AUTHOR:**

Name:Anagha Ashok



 
