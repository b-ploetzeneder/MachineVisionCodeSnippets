---
permalink: /docs/cumulative/
title: "CIMAQ_Cumulative_Histogram.vi"
excerpt: "calculates the cumulative histogram and percentile values."
last_modified_at: 2018-09-13T11:31:38-04:00
redirect_from:
  - /theme-setup/
toc: true 
---

This function calculates the cumulative histogram of a function and two percentile values (I often use 5%/95% or 10%/90% values instead of min/max, because they are more robust to noise).

<figure>
  <img src="{{ '/assets/images/subvis/cumulative_overview.png' | relative_url }}" alt="Cumulative Histogram and Percentiles">
</figure>  
## Code

Function: [CIMAQ_Cumulative_Histogram.vi](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/user.lib/ CIMAQ_Cumulative_Histogram.vi)

<figure>
  <img src="{{ '/assets/images/subvis/cumulative_function.png' | relative_url }}" alt="CIMAQ_Cumulative_Histogram.vi">
</figure>


 
## Inputs


| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Image|  anything that works with IMAQ Histogram (grayscale) |
| Nr of classes (optional)|  same as with IMAQ Histogram, 256 = default |
| Percentile 1 (optional)|  first percentile that is calculated, should be from 0-100. 10=default |
| Percentile 2 (optional)|  second percentile that is calculated, 90 = default|


## Outputs

| Name                                        | Description                                           |
| ------------------------------------------- | ----------------------------------------------------- |
| Cumulative Histogram | Array with integrated histogram |
| Percentile 1 (optional)|  first percentile (min / max values depend on datatype - the function scales|
| Percentile 2 (optional)|  second percentile|


## How to use it

I put an [example program](https://github.com/b-ploetzeneder/MachineVisionCodeSnippets/blob/master/examples/Cumulative.vi) on Github.

<figure>
  <img src="{{ '/assets/images/subvis/cumulative_example.png' | relative_url }}" alt="Example program for CIMAQ_Cumulative_Histogram.vi">
</figure>

## How does it work?
 
 It simple integrates the histogram. It also calculates the percentiles based on area.
 <figure>
  <img src="{{ '/assets/images/subvis/cumulative_source.png' | relative_url }}" alt="Source">
</figure>
