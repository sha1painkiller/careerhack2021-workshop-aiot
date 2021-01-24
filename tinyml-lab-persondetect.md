# Tiny Machine Learning lab on Azure Sphere

## Train a person detection ML model
1. Create a small TensorFlow Lite model that can fit into the device 
    - [training a person detection model](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#training-a-model)
    - [understand the architecture - MobileNets](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#understanding-the-architecture)
1. Convert the model to FlatBuffer
    - [Quantizing and converting to TensorFlow Lite](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#quantizing-and-converting-to-tensorflow-lite)
1. Convert the FlatBuffer to C Array
    - [Converting into a C source file](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/lite/micro/examples/person_detection/training_a_model.md#converting-into-a-c-source-file)
1. Move the array C and header files to the project space
    - for ex: {ROOT}/tinyml-lab-visionkit/MT3620_M4_NeuroPilot-Micro/app/lib_src/person_detection_demo/
        - person_detect_model_data.cc
        - person_detect_model_data.h
1. Inference Model framework
    - {ROOT}/tinyml-lab-visionkit/MT3620_M4_NeuroPilot-Micro/app/lib_src/person_detection_demo/main.cc
    - configure model input/output
    - built together with model CC files as a static library for external linkage

## Integrate the (above) ML inference model with Azure Sphere RT (M4) core projects
MT3620 M4 core is used for ML computation in this context
1. launch Visual Studio and open rt-core project CMakeListx.txt
    - {root}/MT3620_M4_NeuroPilot-Micro/app/vs_project/rtcore/CMakeList.txt

    ![](./images/open-cmake.png)
1. open Azure Sphere CLI in **administrator** privilege mode, and type 
    > azsphere device edv -r
    
    to enable Azure Sphere M4 core debug mode
1. build and deploy the images to Azure Sphere M4 core

    ![](./images/vs-rt-f5run.png)
1. stop the debugger

## High-Level (A7) Core project
MT3620 A7 core is used to handle system input(camera)/output(cloud connection) and interact with M4 ML model.
1. launch Visual Studio and open HL-core project CMakeListx.txt
    - {root}/MT3620_M4_NeuroPilot-Micro/app/vs_project/hlcore/CMakeList.txt

    <!--- ![](./images/open-cmake.png) --->
1. build and deploy the image to Azure Sphere A7 core

    ![](./images/vs-hl-f5run.png)
---

## Block diagram
![](./images/mt3620-vision-ml-diagram.png)

## Documentation
note: the documents can only be available after signing an EULA agreement with MediaTek. Check the [MediaTek website](https://neuropilot.mediatek.com/resources/public/latest/en/docs/npu_introduction) for more informatio.
{root}/MT3620_M4_NeuroPilot-Micro/doc/*
- NeuroPilot-Micro MT3620 Demo v0.2 20200710.pdf
- NeuroPilot-Micro MT3620 Getting started v0.2 20200710.pdf
- NeuroPilot-Micro MT3620 Introduction v0.2 20200710.pdf
- NeuroPilot-Micro MT3620 User Guide v0.2 20200710.pdf