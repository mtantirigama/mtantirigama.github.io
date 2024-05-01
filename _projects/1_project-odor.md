---
layout: page
title: Analysing odor coding from imaging data
description: Pipeline for processing imaging data to analyse how odor information is organized
img: assets/img/project-odor/brain-smelling.png
importance: 1
category: work
related_publications: false
images:
  compare: true
  slider: true
---

# Analysing odor coding from imaging data
- [Grand challenge - Neural coding](#grand-challenge-Neural-coding)
- [Movement correction](#movement-correction)
- [Neuron segmentation](#neuron-segmentation)
- [Neuron activity time-series](#neuron-activity-time-series)
- [Odor maps](#odor-maps)

## Grand challenge - Neural coding
### The grand challenge is to understand how activity in the brain represents information about the outside world. 

A microscope is used to acquire movies containing activity of neurons. This raw data is processed to acquire information about their behavior during an event in the outside world. In this case, exposure to an odour - ethyl butyrate - which has the distinct smell of pineapple. An example movie is below showing the activity of hundreds of neurons during the exposure to the odour. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/gcamp-with-traces.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Two example traces for the neurons highligted with arrows are shown above. The change in intensity corresponds to their level of activity. The neuron highlighted in red shows an increase in activity in the presence of the odor ethyl butyrate, while the neuron highlighted in blue shows a reduction in activity during exposure to the same odor. 
</div>

The challenge is to figure out how the changes in the activity of neurons encode information about the odour exposure - so that we know how neurons represent what is happening in the outside world. 

## Movement correction

Before analysis, any movement in the movie has to be corrected. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/movement-stacks.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Data before and after correcting for movement. 
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/pexels-engin-akyurt-6069112-960x540-30fps.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Test. 
</div>

## Neuron segmentation

The next step is to identify individual neurons as regions-of-interests (ROI). Then extract the changes in pixel intensity as a time-series.

<img-comparison-slider>
  {% include figure.liquid path="assets/img/project-odor/cell-segment.png" class="img-fluid rounded z-depth-1" slot="first" %}
  {% include figure.liquid path="assets/img/project-odor/cell-segment-roi.png" class="img-fluid rounded z-depth-1" slot="second" %}
</img-comparison-slider>

## Neuron activity time-series

## Odor maps



---
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% testing column writing %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        testing column writing without curly brackets
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
