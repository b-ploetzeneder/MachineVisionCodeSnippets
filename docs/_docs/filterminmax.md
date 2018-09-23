---
permalink: /docs/filterminmax/
title: "CIMAQ_ParticleFilter_MinMax.vi	"
excerpt: "Filter Min/Max."
last_modified_at: 2018-09-19T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function sorts a particle by a given parameter (for example: the area) and the removes all but the largest (default) or smallest.

<figure>
  <img src="{{ '/assets/images/subvis/CIMAQ_PF_minmax.gif' | relative_url }}" alt="Using CIMAQ_PM_BoundingC.vi">
</figure>
## Code

Function: [CIMAQ PM_BoundingC.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ_PM_BoundingC.vi)

<figure>
  <img src="{{ '/assets/images/subvis/enclosingcircle_function.png' | relative_url }}" alt="Using CIMAQ_PM_BoundingC.vi">
</figure>


Dependencies:

 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image | U8 image containing binary particles. |
| Parameter|  Parameter that is inspected (default: area) |
| Mode|  Maximal (default) or minimal sorting |



## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image | Modified image |
 

## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/Particle_MinMaxFilter.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/maxfilter_example.png' | relative_url }}" alt="Example program for CIMAQ_ParticleFilter_MinMax.vi">
</figure>

## How does it work?

 