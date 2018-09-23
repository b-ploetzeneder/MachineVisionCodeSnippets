---
permalink: /docs/maxmin/
title: "CIMAQ MaxMin.vi"
excerpt: "Finds the minimal and maximal intensity in an image."
last_modified_at: 2018-09-23T21:20:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

Quick little helper function that extracts the minimal and maximal intensity in an image. Equivalent to unbundling `IMAQ Histogram`, just less clicks and less mess.
  
## Code

Function: [CIMAQ MaxMin.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ_MaxMin.vi)

<figure>
  <img src="{{ '/assets/images/subvis/maxmin_function.png' | relative_url }}" alt="Using CIMAQ_MaxMin.vi">
</figure>


Dependencies:

 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image | Any grayscale image |

 

## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Maximal Value, Minimal Value | see: histogram |
 

## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/MaxMin.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/maxmin_example.png' | relative_url }}" alt="Example program for CIMAQ_MaxMin.vi">
</figure>

## How does it work?

Really just an encapsulation of `IMAQ Histogram`