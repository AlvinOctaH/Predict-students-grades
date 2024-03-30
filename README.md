# RNN PyTorch

----------------
## Table of contents

- [Introduction to RNN and PyTorch](#Introduction-to-RNN-and-PyTorch)
  - What is Recurrent Neural Network (RNN)?
  - What is PyTorch?
- [Preparing the dataset](#Preparing-the-dataset)
  - Heatmap
  - Data Preprocessing
- [RNN Structure](#RNN-Structure)
- [Result](#Result)

----------
## Introduction to RNN and PyTorch
### What is Recurrent Neural Network (RNN)?
<p align="justify">
A recurrent neural network (RNN) is a type of artificial neural network that is particularly well-suited for processing sequential data or time series data. Unlike traditional feedforward neural networks, RNNs have loops in their network which allow information to persist and be passed from one step to the next. This allows them to effectively model and learn from sequential patterns and dependencies in data, such as those found in natural language, speech, handwriting, or sensor data. The key to this capability is the hidden state (or memory) within the RNN's internal loops, which captures information about what has been calculated previously. This hidden state acts as an internal memory that updates at each time step as it processes new inputs, informed by its prior state. Through this recurrent structure and dynamic memory ability, RNNs can very naturally process inputs of varying lengths. While powerful, training traditional RNNs can be challenging due to exploding or vanishing gradient problems. However, more sophisticated RNN architectures like LSTMs and GRUs have been developed to help mitigate these issues. 
</p>

<p align="center">
    <img width="600" src="https://media.geeksforgeeks.org/wp-content/uploads/20231204125839/What-is-Recurrent-Neural-Network-660.webp" alt="Recurrent Neural Network (RNN">
</p>

**Source :** [geeksforgeeks.org](https://www.geeksforgeeks.org/introduction-to-recurrent-neural-network/), [amazon.com](https://aws.amazon.com/what-is/recurrent-neural-network/#:~:text=A%20recurrent%20neural%20network%20(RNN,complex%20semantics%20and%20syntax%20rules.)).

### What is PyTorch?
<p align="justify">
PyTorch is an open-source machine learning (ML) framework based on the Python programming language and the Torch library. Torch is an open-source ML library used for creating deep neural networks and is written in the Lua scripting language. It's one of the preferred platforms for deep learning research. The framework is built to speed up the process between research prototyping and deployment. 
</p>

**Source :** [techtarget.com](https://www.techtarget.com/searchenterpriseai/definition/PyTorch), [pytorch.org](https://pytorch.org/).

## Preparing the dataset 
<p align="justify">
This repository uses a dataset of semester results of engineering students from a university. This data was obtained from Kaggle and titled "<a href="https://www.kaggle.com/datasets/sankha1998/student-semester-result/data">Semester Result of Technical Students</a>". The dataset contains information about students' performance, including their roll numbers (converted to random numbers for privacy), college code, subjects taken, and the semester CGPA (Cumulative Grade Point Average) achieved. It represents a real-world scenario where predicting a student's future academic performance can be challenging. According to the dataset provider, predicting the next semester's CGPA is a complex task. However, analyzing a student's past performance can provide valuable insights for making such predictions.
</p>

### 1. Heatmap
<p align="justify">
The first step of preparing the dataset is to look for correlations between variables using heatmaps to take important variables that can be used as RNN input. Heatmaps are effective for visualizing large datasets by representing data values with colors. This allows data scientists and software engineers to quickly identify patterns, trends, and variations in the data. The implementation of the heatmap is shown in the following figure:
</p>
<p align="center">
    <img width="600" src="https://github.com/AlvinOctaH/Deeplearning-RNN-PyTorch/blob/main/assets/Heatmap_RNN.png" alt="Heatmap">
</p>
<p align="justify">
In this repository I use RNN to predict semester 5 grades. As can be seen from the heatmap, only semester 1 to 4 grade variables are correlated with semester 5 grades, so those grades will be the input features for RNN.
</p>

### 2. Data Preprocessing
<p align="justify">
Data preprocessing in the case of this dataset is done by removing variables or columns from the dataset that are not needed, then cleaning the data from missing or NaN values. The results of data preprocessing get 169 rows of clean data, the results can be seen in the following figure:
</p>
<p align="center">
    <img width="300" src="https://github.com/AlvinOctaH/Deeplearning-RNN-PyTorch/blob/main/assets/datacleaned.png" alt="Data Preprocessing">
</p>

## RNN Structure
<p align="justify">
To build an RNN structure for predicting exam scores based on the scores of four previous exams, I would start by loading the data from an Excel file and preprocessing it by converting it into PyTorch tensors and splitting it into train and test sets. Next, I would define the RNN model architecture with the following parameters: input size of 4 (number of features), hidden size of 64 (size of the hidden state in the RNN), output size of 1 (single output value), number of layers of 3 (number of recurrent layers), and dropout rate of 0.2 (dropout rate for regularization). The RNN model architecture would include a recurrent layer that takes in the input features and outputs a hidden state, which is then passed through a fully connected layer to output a single value. The RNN model would be initialized with random weights, and the hidden state would be initialized with zeros.
</p>
<p align="justify">
Next, I would define the loss function and optimizer for training the RNN model. I would use the mean squared error (MSE) loss function and the Adam optimizer with a learning rate of 0.001 and weight decay for regularization. I would then train the RNN model for 1000 epochs, updating the model parameters using backpropagation and printing the training loss for every 100 epochs. I would also evaluate the RNN model on the test set and print the test loss.
</p>
<p align="justify">
Finally, I would save the predicted scores and the testing data to Excel files for further analysis. The RNN model can be customized by adjusting the hyperparameters and input features as needed for other regression tasks involving sequential data. For example, I could increase the number of recurrent layers or the hidden size to capture more complex patterns in the data, or I could add additional input features such as the student's attendance, grades, and behavior. I could also adjust the learning rate, dropout rate, or weight decay to improve the model's performance.
</p>

## Result
<p align="justify">
The test loss of 0.2261 indicates the accuracy of the trained RNN model in predicting GPA scores based on the scores of four previous exams. In this case, the test loss is a measure of the difference between the predicted GPA scores and the actual GPA scores in the test set, calculated using the mean squared error (MSE) loss function.
</p>
<p align="justify">
The MSE loss function measures the average squared difference between the predicted and actual GPA scores and is a common metric for evaluating the accuracy of regression models. In this case, a test loss of 0.2261 indicates that the average squared difference between the predicted and actual GPA scores in the test set is 0.2261.
</p>
<p align="justify">
Overall, the test loss of 0.2261, as calculated using the MSE loss function, suggests that the RNN model is a promising tool for predicting GPA scores based on the scores of four previous exams. However, further refinement and customization of the model may be necessary to improve its accuracy and generalizability. It is important to evaluate the performance of the model using other metrics, such as the mean absolute error or the R-squared value, to get a more complete picture of the model's accuracy. Additionally, the test loss should be interpreted in the context of the specific problem and dataset, as a high test loss may still result in significant errors in the predicted GPA scores. The result of the test loss can be seen in the following figure:
</p>
<p align="center">
    <img width="200" src="https://github.com/AlvinOctaH/Deeplearning-RNN-PyTorch/blob/main/assets/result_MSE.png" alt="result_training_test">
</p>
