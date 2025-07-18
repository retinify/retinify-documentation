---
title: Installation
layout: default
nav_order: 2
---

# Installation
retinify supports Linux (Ubuntu) and can be easily installed using the provided `build.sh` script.  
This script generates a Debian package, enabling clean installation, easy updating, and simple removal using standard package management tools.  

# 0. Dependencies
- [**GCC 11 or later**](https://gcc.gnu.org/releases.html)
- [**CMake 3.14 or later**](https://cmake.org/download/)
- [**OpenCV 4.6 or later**](https://opencv.org/releases/)
      
    {: .note }
    >If you do not use the `--tools` option, OpenCV is not required.
    
# 1. Clone the retinify repository.
```bash
git clone https://github.com/retinify/retinify.git
cd retinify
```

# 2. Install retinify
Select the hardware backend (e.g., NVIDIA GPU or CPU) to be used for acceleration, then run the installation script with the appropriate options.
  
{: .highlight }
>If you do not add `--install`, a Debian package will just be created in the build directory.  

## 2.1 with TensorRT
  
| Libraries    | [CUDA](https://developer.nvidia.com/cuda-toolkit-archive) | [cuDNN](https://developer.nvidia.com/cudnn-archive) | [TensorRT](https://developer.nvidia.com/tensorrt) |  
|:-------------|:--------|:--------|:---------|  
| Versions     | `12.x`  | `9.x`   | `10.x`   |  
  
```bash
./build.sh --install --tensorrt --tools
```

## 2.2 with CPU
```bash
./build.sh --install --cpu --tools
```

## 2.3 with HailoRT
coming soon

## 2.4 with OpenVINO
coming soon

# 3. Verify Installation
```bash
dpkg -l libretinify-dev
```
  
# 4. Uninstall retinify
```bash
sudo apt remove libretinify-dev
```
  
{: .note }
>This option is only available if you installed retinify using the generated Debian package.
  
