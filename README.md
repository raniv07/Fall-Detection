# Fall-Detection using Multimodal data

## Introduction

In this project, we propose a fall detection system that combines sensor and camera data using a concatenation model to improve the accuracy of fall detection. We extract features from both sensor and camera data and use a feature selection technique to identify the most relevant features for each type of data. Our proposed system uses a Random Forest classifier to take advantage of the unique information provided by each type of data. We aim to explore additional feature extraction techniques, investigate the impact of different types of sensors and cameras, and evaluate the effectiveness of real-time fall detection in future work.
Our goal is to develop a reliable and accurate fall detection system that can improve the safety and well-being of older adults at risk of falling.

### Files in repository
- load_data.ipynb
    - Notebook for loading and visualizing sensor data.
    - Prepares data for input into the main detection pipeline.
      
- Model.ipynb
    -  Final version notebook implementing fall detection pipeline.
    -  Contains final model implemnted for two class to detect fall and all other activities considered as non-fall.

- HumanFallDetection_final.ipynb
    -  Main notebook implementing fall detection pipeline.
    -  Contains final model implemnted on further human activities.



