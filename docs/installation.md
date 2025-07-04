---
title: Installation
layout: default
nav_order: 2
---

# Installation


# 1. Clone the retinify repository.
```
git clone --recursive https://github.com/retinify/retinify.git
cd retinify
```

# 2. Install retinify
## 2.1 with NVIDIA GPU
  
| Libraries    | [CUDA](https://developer.nvidia.com/cuda-toolkit-archive) | [cuDNN](https://developer.nvidia.com/cudnn-archive) | [TensorRT](https://developer.nvidia.com/tensorrt) |
|--------------|---------|---------|----------|
| Versions     | `12.x`  | `9.x`   | `10.x`   |
```
./build.sh --install --gpu
```

## 2.2 with CPU
```
./build.sh --install --cpu
```

---
>[!TIP]
>If you do not add `--install`, a Debian package will just be created in the build directory.

# 3. Uninstall retinify
```
sudo apt remove libretinify-dev
```
> [!NOTE]
> Only available if you installed the Debian package via the build script.