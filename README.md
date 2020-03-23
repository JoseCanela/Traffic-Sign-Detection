# U.S. Traffic Sign Detection Using Convolutional Neural Networks - YOLOv3
## Overview
* Developed an object detection model that identifies the presence, location, and type of one or more U.S. traffic signs in a given photograph using the LISA dataset — currently the largest known dataset of U.S. traffic signs with 47 different types of U.S. traffic signs.
* This group project involved exploratory data analysis (EDA), annotation preprocessing, memory reduction, parameter tuning, and training and testing a convolutional neural network-based object detection algorithm (YOLOv3) for maximum average precisions (AP) for each type of U.S. traffic sign, maximum intersection of union (IoU), and maximum mean average precision (mAP). Our final (best) results were a maximum IoU of 68% and a maximum mAP of 65%. 

## LISA Traffic Sign Dataset
* The [LISA Traffic Sign Dataset](http://cvrr.ucsd.edu/LISA/lisa-traffic-sign-dataset.html) is a set of annotated frames of US traffic signs.
* The dataset has the following characteristics:
  * 47 types of signs (classes)
  * 7855 annotations (signs) on 6610 frames (images)
  * Sign sizes from 6x6 to 167x168 pixels
  * Image sizes from 640x480 to 1024x522 pixels
  * Images vary between color and grayscale
  * Annotations include sign type, position, size, occluded (yes/no), on side road (yes/no).
## Annotation Preprocessing
* Convert images from png to jpg
* For each image, exported an annotation file
  * Each annotation files contained an image and bounding box locations of the signs.
  * In order to train our CNN, we needed to normalized dimensions of bounding box relative to image.
  ![Screen Shot 2020-03-23 at 2 21 42 AM](https://user-images.githubusercontent.com/56474640/77287934-1a9f2200-6cad-11ea-936d-e945c5caa569.png)
  
* Update configuration file to train our dataset
* Processed data from LISA dataset
  * Created files that stored information about location of objects in images
* Made sure all file paths to images were accurate

## Training our YOLOv3 Convolution Neural Network Model 
* Trained on 75% of the images in LISA dataset.
* We utilized *Darknet*, a wrapper around the YOLOv3 algorithm.
* **GOOGLE COLAB WAS OUR SAVIOR!**
  * We conducted training in Google Colab for *hosted GPU connected runtime*. 
    * **Decreased runtime by a factor of 30 relative to running locally**
    * **Uploaded all images and their annotations to Google Drive**
    * **Saved weights to local machine every 100 iterations**
* Darknet outputs a weights file which holds information about important features
* We trained our model for 3000 iterations.
  * Recommended iterations = 2000 * classes 
    * **Unable to do so due to the time contraints imposed by our professor**

## What is YOLOv3?
*
* For more details on YOLOv3 theory: https://medium.com/analytics-vidhya/yolo-v3-theory-explained-33100f6d193

## Dependencies
* **Darknet** is a wrapper around the YOLOv3 Convolutional Neural Network algorithm. More specifically, it is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation. 
  * We used the following link for [Darknet implementation instructions](https://github.com/AlexeyAB/darknet/blob/master/README.md#yolo-v3-in-other-frameworks). When we read through the README.md file, we click on bullet point (6) in order to learn how to train our model to detect custom objects.
    * For addition details: https://pjreddie.com/darknet/yolo/

## Authors
![Nishant Sinha](https://avatars1.githubusercontent.com/u/46798485?s=400&u=e15e4723b7b3729b1d8f65fe2da44c519c7df345&v=4) | ![Arjun Mitra](https://avatars1.githubusercontent.com/u/42727780?s=400&v=4) | 
----------------------------------------------------------- | ----------------------------------------------------------- |
[Nishant Sinha](https://github.com/sinha-nishant) | [Arjun Mitra](https://github.com/arjunmitra) | [Patrick Condie]

![Patrick Condie](https://avatars2.githubusercontent.com/u/42784051?s=400&v=4) | ![Jose Canela](https://avatars1.githubusercontent.com/u/56474640?s=400&u=f847953fb3b95a50302bc3503c5837d01b9cfafd&v=4) | 
----------------------------------------------------------- | ----------------------------------------------------------- |
[Patrick Condie](https://github.com/pcondie) | [Jose Canela](https://github.com/JoseCanela)

## Citations
Andreas Møgelmose, Mohan M. Trivedi, and Thomas B. Moeslund, "Vision based Traffic Sign Detection and Analysis for Intelligent Driver Assistance Systems: Perspectives and Survey," IEEE Transactions on Intelligent Transportation Systems, 2012.

## Project Status
### Further work may be done in the future.
* Our model can be implemented to assess traffic signs from cars in real time
  * However, need to improve the classification of low quantity signs
* Future suggestions:
  * Normalize all images to grayscale
  * Oversample images to fix class imbalance through image augmentation
    * Blur images (Gaussian Blur)
    * Sharpening images (Unsharp Mask)
  * Focus on training specific classes for higher accuracy
  * Factoring occluded signs into the model differently
