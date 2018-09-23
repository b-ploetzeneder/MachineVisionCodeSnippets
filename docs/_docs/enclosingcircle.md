---
permalink: /docs/enclosingcircle/
title: "CIMAQ PM_BoundingC.vi"
excerpt: "Calculating the minimal enclosing circle."
last_modified_at: 2018-09-19T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function calculates the minimal enclosing circle of a particle in an image.

![image-center]({{ "/assets/images/subvis/enclosingcircle_concept.png" | relative_url }}){: .align-center}
  
## Code

Function: [CIMAQ PM_BoundingC.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/CIMAQ_PM_BoundingC.vi)

<figure>
  <img src="{{ '/assets/images/subvis/enclosingcircle_function.png' | relative_url }}" alt="Using CIMAQ_PM_BoundingC.vi">
</figure>


Dependencies:

 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image | U8 image containing exactly 1 binary particle. |
| Speedup|  Constant that makes the algorithm faster, and more unprecise (we just scale the input image..) |

**Warning:** Ensure that the image contains only 1 binary particle. Make sure that the image is large enough to contain the center of the circle.
{: .notice--info}


## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Center | Center of the minimal enclosing circle |
| Radius|  Radius of the minimal enclosing circle |
| Bounding box|  Bounding box - mostly for use with Overlay Oval.. |


## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/Particle_Enclosing_Circle.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/enclosingcircle_example.png' | relative_url }}" alt="Example program for CIMAQ_PM_BoundingC.vi">
</figure>

## How does it work?

There are [plenty of algorithms](https://en.wikipedia.org/wiki/Smallest-circle_problem) for this problem; I chose one that is easy to understand, although it is not the fastest.

The implementation is based on 3 ideas:
- The center of the circle is somewhere in the image (this has to be ensured by the user)
- The only points that can define the circle lie on the Convex Hull
- The center of the circle lies on the watershed lines of the Convex Hull (this is not so self-evident, but you can read the [paper] (https://ieeexplore.ieee.org/document/4567872/)

I brute-force the search of the minimal circle by
- calculating each possible center (based on IMAQ Watershed)
- testing each center by calculating the maximal distance to each point on the convex hull contour (this is the radius of a enclosing circle going through that center)
- selecting the center point that produces the smalles radius