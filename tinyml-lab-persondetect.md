# Tiny Machine Learning lab on Azure Sphere

## Train a person detection ML model
1. Create a small TensorFlow Lite model that can fit into the device 
    - [training a person detection model](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#training-a-model)
    - [understand the architecture - MobileNets](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#understanding-the-architecture)
2. Convert the model to FlatBuffer
    - [Quantizing and converting to TensorFlow Lite](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#quantizing-and-converting-to-tensorflow-lite)
3. Convert the FlatBuffer to C Array
    - [Converting into a C source file](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#converting-into-a-c-source-file)
4. move the array file to the project space

## Integrate the model with Azure Sphere M4 projects
1. start Visual Studio and open the target cmake file
2. open Azure Sphere CLI in administrator privelege, and type "azsphere device edv -r" to enable Azure Sphere M4 core debug mode
3. build and deploy the images to Azure Sphere M4 core

## High-Level Core (A7) 
1. open HL-core project cmake
2. build and deploy the image to Azure Sphere A7 core

---
---
## Block diagram
![](./images/mt3620-vision-ml-diagram.PNG)
