# AquaVision
Deep Learning based Drowning Detection

# About
Aqua-Vision is a Deep Learning and Imaging based Drowning detection model built to replace full time lifwguards as they are not generally employed in semi public and private pools. The system uses Two cameras (One Underwater and One Overwater) with a Piezoelectric Disk based Hydrohone to classify people as drowning or not drowning , especially for cases hwere a single person is there in the pool .

# Working Principle
The system captures images of a person swimming overwater and underwater and based on the agitation and posture of the person , classifies the image as swimming or drowning. However , since posture of s=every person while swimming in unique , it is not feasible to use just a camera to solve this problem. Therefore, it uses the Audio input from a Hydrohone installed on the swimming pool wall to classify the audio as rhythmic or agitated and combine this with the image classifier to finally detect if the person is swiming or drowning.

# Setup

## 1) Setting Up the Directory
While writing the code , it will be required to load the correct dataset files and directories into the code so that the model can be trained. Thus, keeping all the required resources in one single directory makes the coding easier. 
To set up a directory, navigate to the folder on the system where you want to save the files and code and create a folder of any name (say `Fire_Detection`).The dataset is to be stored in this directory .

## 2)Setting Up the Coding Environment (IDE)
In this implementation, we will be using VS Code IDE to write our codes and implement the image detection.

### Installing VS Code
To install Visual Dtudio Code, you can directly type in *install vs code* on google and install the latest version. 
Here, you can find the tutorial to install VS code and setting up python extension for [Windows](https://www.youtube.com/watch?v=MlIzFUI1QGA) and [Linux](https://code.visualstudio.com/docs/setup/linux).


### Setting Up Jupyter Notebook Extension
To install the jupyter notebook extension, go to the extensions icon in vscode and search *jupyter*. Install the first extension Jupyter by microsoft. 

![image](https://user-images.githubusercontent.com/81915404/162585795-ae35acb2-39c8-4495-8c27-d5ddf4d56cb9.png)

Once jupyter noteebook has been installed , go to the dirctory Fire_Detection and open VS code in that directory. This can be done by going to open in file tab in vscode and typin path of the directory **OR** by going t that directoy, right clicking and choosing the option **open with code**.

For Linux, the following command can be run to open code in the specific directory:
    
    cd <path to the directory>
    code .

So , say my directory is stored in documents an =d is named Fire_Detection. Then, the command will be:

    cd /Documents/Fire_Detection
    code .

After doing this, the open directory in the vs code window will show an empty directory named Fire_Detection.

![image](https://user-images.githubusercontent.com/81915404/162586381-cc4d9315-fe44-45c4-85f7-2081e2e904a7.png)

Next, we need to install the required dependencies (python libraries) to be able to implement our code. 
In this code, we are making use of Tensorflow Library . We will also use numpy to create arrays of images and os to refer our directory thorugh code.

To install these on VS code, go to the terminal and enter the following commands:
    
    pip install tensorflow 
    pip install numpy
    pip install os

## Downloading the Required Files:
The files block of the repository contains three files `fire_detection.ipynb` , `fire_detection.txt` and `fire_detection.py`.

To implement the algorithm, only the jupyter notebook is required i.e. `fire_detection.ipynb`. The other two can be used as references . The text file shows the complete training process steps and the python file contains the complete code as a single file though running it will not give the same output as vscode cannot process images in its terminal.

To set the directory up for implementation, download `fire_detection.ipynb` file in the `Fire_Detection` directory that was initially set up. Next, we need to set up the **Training , Testing** and **Validation** datasets. 

Splitting the dataset into these three sets is a very important task as it decides whether the model will be able to learn the pattern perfectly and be able to identify them or not. The dataset can be split in any way , some of which are shown below. Choosing the right validation dataset is necessary to prevent overfitting as well as underfitting of the model. To understand more about splitting the dataset, you can refer to [this](https://www.v7labs.com/blog/train-validation-test-set) website.

![image](https://user-images.githubusercontent.com/81915404/162608173-322a266b-d620-4a97-baf8-756081cf6ab3.png)

To split the dataset, create afolder in the `Fire_Detection` directry and name it `Dataset_Fire` or any other name as per your choice. Create three folders in this folder `Training` , `Testing` and `Validation`. In the training folder, add 70 - 75 % of your dataset images and add 10 - 15 % of them to the validation dataset. Try to put a high amount of varied images in the validation dataset for better fitting. Add the rest of the images in the testing dataset. 

In the `Trainng` and `Vaidation` folders, seperate the fire and non fire images into `fire` and `non_fire` folders while in the `Testing` folder, let there be all images at the same place.

This allows the model to train to be able to classify the images as fire or non fire.

After finishing this, the directory will look like this:

![image](https://user-images.githubusercontent.com/81915404/162608510-8bfab761-0b0c-4339-8bec-8e388901a241.png)

# Implementation
## CNN
The Model takes input of video fromm camera , and classifies every image as Drowning or Swimming . 
Some Test Runs: 

### **Underwater Images:**
__Non Drowning__

![image](https://user-images.githubusercontent.com/81915404/230651396-e15de163-1276-4502-9ae9-c46114a015d6.png)
![image](https://user-images.githubusercontent.com/81915404/230652271-7604e4be-6e61-413f-99be-b0ed5e8c3674.png)

__Drowning__

![image](https://user-images.githubusercontent.com/81915404/230652308-e2cfa6bb-eff3-40b9-9190-b9ae4b889bf2.png)
![image](https://user-images.githubusercontent.com/81915404/230652840-17848d72-3642-4db2-9eaf-00dc3bdab696.png)

### **Overwater Images:**
__Non Drowning__

![image](https://user-images.githubusercontent.com/81915404/230652597-88a7652e-5a7e-4673-b363-fd5cc96b0c8a.png)
![image](https://user-images.githubusercontent.com/81915404/230652641-97695b59-e5ee-48af-a540-efd64c057dda.png)

__Drowning__

![image](https://user-images.githubusercontent.com/81915404/230652508-6f2a0dfd-dac2-4957-ae35-430de1a7b21f.png)
![image](https://user-images.githubusercontent.com/81915404/230652540-6414097a-d619-4d41-9569-5d244e9ad99c.png)

