---
permalink: /docs/enclosingcircle/
title: "CIMAQ PM_BoundingC.vi"
excerpt: "Calculating the minimal enclosing circle."
last_modified_at: 2018-09-19T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

Calculating the minimal enclosing circle



 
![image-center]({{ "/assets/images/subvis/enclosingcircle_concept.png" | relative_url }}){: .align-center}
  
## Code

Function: CIMAQ PM_BoundingC.vi

<figure>
  <img src="{{ '/assets/images/subvis/enclosingcircle_function.png' | relative_url }}" alt="bundle install in Terminal window">
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


<figure>
  <img src="{{ '/assets/images/subvis/enclosingcircle_example.png' | relative_url }}" alt="bundle install in Terminal window">
</figure>

## How does it work?

The implmentation is based on 3 ideas:
The center of the circle is somewhere in the image (this has to be ensured by the user)
The only points that can define the circle lie on the convex Hull
The center of the circle lies on the watershed lines of the convex hull
We brute-force finding a minimal circle by calculating the distances between all potential centers + points lying on the circle.
