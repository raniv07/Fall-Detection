# Fall-Detection using Multimodal data

## Introduction

In this project, we propose a fall detection system that combines sensor and camera data using a concatenation model to improve the accuracy of fall detection. We extract features from both sensor and camera data and use a feature selection technique to identify the most relevant features for each type of data. Our proposed system uses a Random Forest classifier to take advantage of the unique information provided by each type of data. We aim to explore additional feature extraction techniques, investigate the impact of different types of sensors and cameras, and evaluate the effectiveness of real-time fall detection in future work.
Our goal is to develop a reliable and accurate fall detection system that can improve the safety and well-being of older adults at risk of falling.

## Files in repository
- load_data.ipynb
    - Notebook for downloading and forming sensor and camera data.
    - Prepares data for input into the main detection pipeline.
      
- Model.ipynb
    -  Final version notebook implementing fall detection pipeline.
    -  Contains final model implemnted to detect fall and non-fall (for two class).

- HumanFallDetection_final.ipynb
    -  Main notebook implementing fall detection pipeline.
    -  Contains final model implemnted on further human activities (extended to human activities from suggestion of reviewing panel).


### Dataset

We employ Panamerican University’s [UP-FALL detection dataset](https://www.mdpi.com/1424-8220/19/9/1988). This dataset is used to recognize human activities and is mostly used to identify older people’s falls.This dataset contains two different categories of data. One is the picture data that the cameras have recorded, and the other is the sensor data that has been saved as a CSV file.

### Pre-processing 

The main objective of this project was to detect falls and non-fall which was extended to detect human activity based on the suggestions from reviewing panel. In the preprocessing stage, we initially changed the labels to only 2 classes i.e. fall and non-fall which was later shifted to include all the behavioral activities labels. Our main objective was stretched and shifted to determine that human activity occurs on a frame-by-frame basis. Moreover, the original dataset included 17 subjects but we only used data from 1 subject. In the preprocessing stage i.e. preparing data to load into our model we created a sensor.csv file
which had all the values concatenated for each trial of all activities and then classified video sequences frame-by-frame.

### Multimodal approach

In order to cater to two types of data i.e. data from sensors and then using data from cameras we designed the following neural network architecture. We extracted features from input data obtained from each camera. Two input data from two cameras are passed through CNN architecture.Then to proceed with sensor data, it is passed through one convolution 1D layer and the Relu activation function. Next, these computed vectors from sensors and two cameras continue passing through one max pooling 1D layer, one batch normalization layer, and a flattened layer. Subsequently, these three flattened layers are concatenated as a final feature vector before going through two fully connected layers. Next, the dropout layer with a rate of 0.2 is added for regularization, and the final result can be computed via a Softmax layer at the end for classifying fall detection.

![image](https://github.com/user-attachments/assets/45b26b58-0be5-408d-8c11-a2e254ef949b)

## Result 
In experiments, we analyze the performance by combining: the sensor dataset (S), two cameras that are Camera 1 (C1) and Camera 2 (C2), to get (S+C1+C2). Then we measure all results using four metrics, including Accuracy, Precision, Recall, and F1-Score.

![image](https://github.com/user-attachments/assets/cd34ec82-ee61-4347-b3be-199170bdf220)

It is noteworthy that our approach was able to circumvent all of Martinez et al.’s techniques (which was introduced while doing literature survey),including Random Forest, Support Vector Machines, Multi-Layer Perceptron, and K-Nearest Neighbors. Comparison is mentioned in our notebooks.





