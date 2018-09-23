---
permalink: /docs/highlight/
title: "CIMAQ_GetHighlightKernel.vi"
excerpt: "calculates a Highlight convolution kernel."
last_modified_at: 2018-09-19T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function calculates a Highlight kernel like the one you get from Vision Assistant. This functions emphasizes ("highlights") edges.
 

<figure>
  <img src="{{ '/assets/images/subvis/GetHighlightKernel.gif' | relative_url }}" alt="Effect of a Highlight Kernel">
</figure>
 
## Code

Function: [CIMAQ GetHighlightKernel.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ GetHighlightKernel.vi)

<figure>
  <img src="{{ '/assets/images/subvis/highlight_function.png' | relative_url }}" alt="CIMAQ_GetHighlightKernel.vi">
</figure>


 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Kernel Size|  defines how big the kernel should be. I automatically turn it into an odd nr | 

## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Kernel | Highlight Kernel of any size |


## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/HighlightKernel.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/highlight_example.png' | relative_url }}" alt="Example program for CIMAQ_GetHighlightKernel.vi">
</figure>

## How does it work?

Just plugs in the equation for the Highlight. Uses a matrix product to reduce nr of calculations.