# RNN PyTorch

----------------
## Table of contents

- [Introduction to RNN and PyTorch](#What-is-Recurrent-Neural-Network-(RNN)?)

----------

## What is Recurrent Neural Network (RNN)?
<p align="justify">
A recurrent neural network (RNN) is a type of artificial neural network that is particularly well-suited for processing sequential data or time series data. Unlike traditional feedforward neural networks, RNNs have loops in their network which allow information to persist and be passed from one step to the next. This allows them to effectively model and learn from sequential patterns and dependencies in data, such as those found in natural language, speech, handwriting, or sensor data. The key to this capability is the hidden state (or memory) within the RNN's internal loops, which captures information about what has been calculated previously. This hidden state acts as an internal memory that updates at each time step as it processes new inputs, informed by its prior state. Through this recurrent structure and dynamic memory ability, RNNs can very naturally process inputs of varying lengths. While powerful, training traditional RNNs can be challenging due to exploding or vanishing gradient problems. However, more sophisticated RNN architectures like LSTMs and GRUs have been developed to help mitigate these issues. 
</p>

<p align="center">
    <img width="800" src="https://media.geeksforgeeks.org/wp-content/uploads/20231204125839/What-is-Recurrent-Neural-Network-660.webp" alt="Recurrent Neural Network (RNN">
</p>

**Source :** [geeksforgeeks.org](https://www.geeksforgeeks.org/introduction-to-recurrent-neural-network/), [amazon.com](https://aws.amazon.com/what-is/recurrent-neural-network/#:~:text=A%20recurrent%20neural%20network%20(RNN,complex%20semantics%20and%20syntax%20rules.)).

## What is PyTorch?
<p align="justify">
PyTorch is an open-source machine learning (ML) framework based on the Python programming language and the Torch library. Torch is an open-source ML library used for creating deep neural networks and is written in the Lua scripting language. It's one of the preferred platforms for deep learning research. The framework is built to speed up the process between research prototyping and deployment. 
</p>

**Source :** [techtarget.com](https://www.techtarget.com/searchenterpriseai/definition/PyTorch), [pytorch.org](https://pytorch.org/).

## Dataset 
