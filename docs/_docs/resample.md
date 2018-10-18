---
permalink: /docs/resample/
title: "CIMAQ_Resample_Proportional.vi"
excerpt: "specify a width or height and it resamples the image but stays proportional."
last_modified_at: 2018-10-17T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function allows you to resample an image proportionally. Just specifify a width or height and it calculates the scaling factor for the other dimension.

## Code

Function: [CIMAQ_Resample_Proportional.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ_Resample_Proportional.vi)

<figure>
  <img src="{{ '/assets/images/subvis/resample_function.png' | relative_url }}" alt="CIMAQ_Resample_Proportional.vi">
</figure>


 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image|  anything that works with IMAQ Resample |
| x-resolution|  desired width |
| y-resolution (optional)|  desired height (only wire one) |
| Method (optional)|  same methods as IMAQ Resample|


## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image|  resulting image |
| x-resolution|  resulting resolution |
| y-resolution |  resulting resolution |


## How to use it

Wire either x-resolution or y-resolution. The vi does the rest.
 
## How does it work?
 
It just calculates the scaling factor by looking at the image size.
