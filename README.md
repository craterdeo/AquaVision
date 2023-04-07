# AquaVision
Deep Learning based Drowning Detection

# About
Aqua-Vision is a Deep Learning and Imaging based Drowning detection model built to replace full time lifwguards as they are not generally employed in semi public and private pools. The system uses Two cameras (One Underwater and One Overwater) with a Piezoelectric Disk based Hydrohone to classify people as drowning or not drowning , especially for cases hwere a single person is there in the pool .

# Working Principle
The system captures images of a person swimming overwater and underwater and based on the agitation and posture of the person , classifies the image as swimming or drowning. However , since posture of s=every person while swimming in unique , it is not feasible to use just a camera to solve this problem. Therefore, it uses the Audio input from a Hydrohone installed on the swimming pool wall to classify the audio as rhythmic or agitated and combine this with the image classifier to finally detect if the person is swiming or drowning.

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

