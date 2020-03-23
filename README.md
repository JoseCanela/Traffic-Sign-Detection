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

## Dependencies
* **Google Colab**
* **Darknet**

## Authors
* Nishant Sinha
* Arjun Mitra
* Patrick Condie
* Jose Canela

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
