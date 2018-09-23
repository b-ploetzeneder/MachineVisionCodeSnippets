---
permalink: /docs/gaussian/
title: "CIMAQ_GetGaussianKernel.vi"
excerpt: "calculates a Gaussian convolution kernel."
last_modified_at: 2018-09-19T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function calculates a Gaussian kernel similar to [IMAQ GetKernel](http://zone.ni.com/reference/en-XX/help/370281AC-01/imaqvision/imaq_getkernel/). Unlike that function, it works with any kernel size. 
Gaussian kernels are mostly used for blurring.

<figure>
  <img src="{{ '/assets/images/subvis/GetGaussianKernel.gif' | relative_url }}" alt="Effect of a Gaussian Kernel">
</figure>  
## Code

Function: [CIMAQ GetGaussianKernel.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ GetGaussianKernel.vi)

<figure>
  <img src="{{ '/assets/images/subvis/gaussian_function.png' | relative_url }}" alt="CIMAQ_GetGaussianKernel.vi">
</figure>


 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Kernel Size|  defines how big the kernel should be. I automatically turn it into an odd nr |
| s(optional)|  Optional input that lets you change the steepness of the Gaussian. |


## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Kernel | Gaussian Kernel of any size |


## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/GaussianKernel.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/gaussian_example.png' | relative_url }}" alt="Example program for CIMAQ_GetGaussianKernel.vi">
</figure>

## How does it work?

Just plugs in the equation for the Gaussian. Uses a matrix product to reduce nr of calculations.