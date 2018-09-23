---
permalink: /docs/filterminmax/
title: "CIMAQ_ParticleFilter_MinMax.vi	"
excerpt: "Filter Min/Max."
last_modified_at: 2018-09-23T21:07:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function sorts a particle by a given parameter (for example: the area) and the removes all but the largest (default) or smallest.

<figure>
  <img src="{{ '/assets/images/subvis/CIMAQ_PF_minmax.gif' | relative_url }}" alt="Using CIMAQ_ParticleFilter_MinMax.vi">
</figure>
## Code

Function: [CIMAQ_ParticleFilter_MinMax.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ_ParticleFilter_MinMax.vi)

<figure>
  <img src="{{ '/assets/images/subvis/pfminmax_function.png' | relative_url }}" alt="Function CIMAQ_ParticleFilter_MinMax.vi">
</figure>


 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image | U8 image containing binary particles. |
| Parameter|  Parameter that is inspected (default: area). Those are the standard parameters from [IMAQ Particle Analysis](http://zone.ni.com/reference/en-XX/help/370281AE-01/imaqvision/imaq_particle_analysis/) |
| Mode|  Maximal (default) or minimal sorting |



## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image | Modified image |
 

## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/Particle_MinMaxFilter.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/particlemax_example.png' | relative_url }}" alt="Example program for CIMAQ_ParticleFilter_MinMax.vi">
</figure>

## How does it work?

I use `IMAQ Particle Analysis` to calculate the selected feature for every particle in the image.
- For the maximal mode, I can just directly create a threshold range for `IMAQ Particle Filter`
- For the minimal mode, I need a second step. The thresholding ranges for `IMAQ Particle Filter` are weirdly defined, so I choose the second smallest particle and create a range from that.

 