---
title: Tutorials
layout: default
nav_order: 3
---

# Tutorials
This tutorial provides a step-by-step guide to using retinify with OpenCV. Please refer to the following repository for the code examples used throughout the tutorial.
  
[Example Repository](https://github.com/retinify/retinify-opencv-template){: .btn }
  
## 1. Install retinify
Please refer to the [Installation](https://retinify.github.io/retinify-documentation/docs/installation.html) section for details.  
  
## 2. Link retinify
We recommend using a CMake-based project when integrating retinify.  
Retinify requires **C++20** and **GCC 11 or later**.  
```cmake
set(CMAKE_CXX_STANDARD 20)

find_package(retinify REQUIRED)

target_link_libraries(${PROJECT_NAME} retinify)
```

## 3. C++ Code
Stereo matching can be performed using the `retinify::Pipeline`.  
In this tutorial, we will use image data in the form of `cv::Mat`.  
  
{: .note }
>The cv::Mat data used as input must satisfy the following conditions:
>- Grayscale
>- Floating-point type (`CV_32FC1`)
>- The left image, right image, and output disparity map must all have the same dimensions.
  
```c++
#include <opencv2/opencv.hpp>

// LOAD GRAYSCALE IMAGES
cv::Mat leftImage = cv::imread(<left_image_path>, cv::IMREAD_GRAYSCALE);
cv::Mat rightImage = cv::imread(<right_image_path>, cv::IMREAD_GRAYSCALE);

// CONVERT TO FLOAT
leftImage.convertTo(leftImage, CV_32FC1);
rightImage.convertTo(rightImage, CV_32FC1);

// PREPARE OUTPUT
cv::Mat disparity = cv::Mat{leftImage.size(), CV_32FC1};
```
```c++
#include <retinify/retinify.hpp>

// RUN STEREO MATCHING
pipeline.Run(leftImage.ptr(), leftImage.step[0], rightImage.ptr(), rightImage.step[0], disparity.ptr(), disparity.step[0]);
```
