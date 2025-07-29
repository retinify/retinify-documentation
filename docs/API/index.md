---
title: API
layout: default
nav_order: 4
---

# Retinify API

Retinify is written in C++ and defined under the `retinify::` namespace.  
The key classes for using Retinify are as follows:
  
- [`retinify::Status`](https://retinify.github.io/retinify-documentation/docs/API/status.html)  
Holds the result of a function call.
- [`retinify::Pipeline`](https://retinify.github.io/retinify-documentation/docs/API/pipeline.html)  
Executes stereo matching on rectified image pairs.
  
>Retinify is designed to avoid throwing exceptions. Instead, it uses `retinify::Status` to report and manage the result of each operation.
  