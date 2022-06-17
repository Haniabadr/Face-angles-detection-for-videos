# Head pose estimation
# Objective :
this project objective is to estimate the head pose angles(row, pitch and yaw) and draw them on the face in the form of axes to a gives input video
# Implementation steps:
* 1- first thing i used Mediapipe to extract the face features, it extracts total of 468 points which maps to 936 features (468 for x axis and 468 for y-axis) 
* 2- then after this i wanted the nose to be the center for all the images so i subtracted the nose values for x-axis and y-axis from all the extracted points
* 3- then in order to make it the same for the model wether the face is near or far from the camera i normalized all the points by dividing them by a fixed distance for all the input frames (this distance that i chose was distance between the nose and the chin), the final results then are stored in a dataframe, each row represents a frame.
* 4-then i applied standard scaler normalization for all the features 
* 5-now the features are ready for training the ML models, i used three different models 

