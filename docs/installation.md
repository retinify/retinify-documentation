---
title: Installation
layout: default
nav_order: 2
---

# Installation
retinify supports Linux (Ubuntu) and can be installed easily via the provided `build.sh` script.  
This script generates a Debian package, allowing for clean installation, easy updates, and simple uninstallation through standard package management tools.

# 1. Clone the retinify repository.
```
git clone --recursive https://github.com/retinify/retinify.git
cd retinify
```

# 2. Install retinify
Select the hardware backend (e.g., NVIDIA GPU or CPU) you want to use for acceleration, then run the installation script with the appropriate options.
## 2.1 with NVIDIA GPU
  
| Libraries    | [CUDA](https://developer.nvidia.com/cuda-toolkit-archive) | [cuDNN](https://developer.nvidia.com/cudnn-archive) | [TensorRT](https://developer.nvidia.com/tensorrt) |  
|:-------------|:--------|:--------|:---------|  
| Versions     | `12.x`  | `9.x`   | `10.x`   |  
  
- `x64` + `NVIDIA GPU`
```
./build.sh --install --gpu
```

## 2.2 with CPU
- `x64`
```
./build.sh --install --cpu
```

---
{: .highlight }
>If you do not add `--install`, a Debian package will just be created in the build directory.  

# 3. Check if Installed
```
dpkg -l libretinify-dev
```
  
# 4. Uninstall retinify
```
sudo apt remove libretinify-dev
```
{: .note }
>Only available if you installed the Debian package via the build script.  
  
