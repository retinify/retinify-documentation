---
title: API
layout: default
nav_order: 4
---

# Retinify API

Retinify is written in C++ and defined under the `retinify::` namespace.  
The key classes for using Retinify are as follows:
  
- [`retinify::Status`]()  
Holds the result of a function call.
- [`retinify::Pipeline`]()  
Executes stereo matching on rectified image pairs.
  
{: .important }
>Retinify is designed to avoid throwing exceptions. Instead, it uses `retinify::Status` to report and manage the result of each operation.
  