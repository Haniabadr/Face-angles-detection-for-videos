# Head pose estimation
# Objective :
This project objective is to **estimate the head pose angles(row, pitch and yaw) and draw them on the face** in the form of axes to a gives input video
# Implementation steps:
* 1- First thing i used Mediapipe to extract the face features, it extracts total of 468 points which maps to **936 features (468 for x axis and 468 for y-axis)** 
* 2- Then after this i wanted the nose to be the center for all the images so i subtracted the nose values for x-axis and y-axis from all the extracted points
* 3- Then in order to make it the same for the model wether the face is near or far from the camera i normalized all the points by dividing them by a fixed distance for all the input frames (this distance that i chose was distance between the nose and the chin), the final results then are stored in a dataframe, each row represents a frame.
* 4- Then i applied standard scaler normalization for all the features 
* 5- Now the features are ready for training the ML models, i used **three different models** , one for predecting row, one for the yaw and the third one for the pitch angle, i applied cross validation (80% of data for training and 20% for validation) , the three models i chose were **XGboost** to handle the unbalanced dataset as some poses in the dataset maybe present more than the other poses 
* 6- And for smoothing the output, After predicting the the three angles i applied an averaging technique so that each frame angles are result of averaging the frames before it (average of max 20 frames or less).
* 7-Then i drew the three axes on the face and saved the video. 
# Instructions:
* For loading the dataset you'll have to drop the dataset path to **path** in **cell number 2**
* And for inserting the testing video you'll need to drop its path to **vid_path** in **cell number 13**

