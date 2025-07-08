---
title: Installation
layout: default
nav_order: 2
---

# Installation
retinify supports Linux (Ubuntu) and can be easily installed using the provided `build.sh` script.  
This script generates a Debian package, enabling clean installation, easy updating, and simple removal using standard package management tools.

# 1. Clone the retinify repository.
```
git clone --recursive https://github.com/retinify/retinify.git
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
  
```
./build.sh --install --gpu
```

## 2.2 with CPU
```
./build.sh --install --cpu
```

## 2.3 with HailoRT
coming soon

## 2.4 with OpenVINO
coming soon

# 3. Verify Installation
```
dpkg -l libretinify-dev
```
  
# 4. Uninstall retinify
```
sudo apt remove libretinify-dev
```
  
{: .note }
>This option is only available if you installed retinify using the generated Debian package.
  
