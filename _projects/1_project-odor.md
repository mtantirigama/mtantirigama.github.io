---
layout: page
title: Analysing odor coding from imaging data
description: Pipeline for processing imaging data to analyse how odor information is organized
img: assets/img/project-odor/brain.png
importance: 1
category: work
related_publications: true
images:
  compare: true
  slider: true
---

- [Grand challenge - Neural coding](#grand-challenge-Neural-coding)
- [Movement correction](#movement-correction)
- [Neuron segmentation](#neuron-segmentation)
- [Neuron activity time-series](#neuron-activity-time-series)
- [Odor maps](#odor-maps)

## Grand challenge - Neural coding
<br>
<div class="row">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-odor/brain-smelling.png" title="brainimage" class="img-fluid" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0 align-self-center">
        The grand challenge is to understand how activity in the brain represents information about the outside world. 
    </div>
</div>
<br>
A microscope is used to acquire movies containing activity of neurons. This raw data is processed to acquire information about their behavior during an event in the outside world. In this case, exposure to an odour - ethyl butyrate - which has the distinct smell of pineapple. An example movie is below showing the activity of hundreds of neurons during the exposure to the odour. 
<br>
<div class="row">
    <div class="col-sm align-items-center">
        {% include video.liquid path="assets/video/gcamp-with-traces.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Two example traces for the neurons highligted with arrows are shown above. The change in intensity corresponds to their level of activity. The neuron highlighted in red shows an increase in activity in the presence of the odor ethyl butyrate, while the neuron highlighted in blue shows a reduction in activity during exposure to the same odor. 
</div>
<br>
The challenge is to figure out how the changes in the activity of neurons encode information about the odour exposure - so that we know how neurons represent what is happening in the outside world. 
<br><br>

---

## Movement correction

Before analysis, any movement in the movie has to be corrected. 
<br>
<div class="row justify-content-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/movement-stacks.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Data before and after correcting for movement. 
</div>
<br><br>

---

## Neuron segmentation

The next step is to identify individual neurons as regions-of-interests (ROI). Then extract the changes in pixel intensity as a time-series.

<style>
  .slider-example-relative-size {
    --default-handle-width: clamp(40px, 10vw, 200px);
  }
</style>
<img-comparison-slider class="slider-example-relative-size">
  {% include figure.liquid path="assets/img/project-odor/cell-segment.png" class="img-fluid rounded z-depth-1" slot="first" %}
  {% include figure.liquid path="assets/img/project-odor/cell-segment-roi.png" class="img-fluid rounded z-depth-1" slot="second" %}
</img-comparison-slider>
<div class="caption">
    Pixels are colored based on co-activity. Then individual neurons are identified as ROIs (cyan borders). 
</div>
<br><br>

---

## Neuron activity time-series

The resulting time-series are noisy. So significant events (*) are captured using a sliding scalable template. This gives a matrix of '[Events, Neurons]', which is used in the final analysis.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project-odor/detectevents.gif" title="templatematching" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Capture significant events using a sliding scalable template.
</div> 
<br><br>

---

## Odor maps

The activity of each neuron is used to identify their response during odour exposure. Neurons that increased their activity are color-coded as red, and neurons that decreased thier activity are color-coded as blue. Thus, an _odor map_ can be visualised for a given odorant, where a **specific odor is represented in the unique combination of neurons that were active or inactive during the odour exposure.**  
<br>
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-odor/map1.png" class="img-fluid rounded" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-odor/map2.png" class="img-fluid rounded" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-odor/map3.png" class="img-fluid rounded" zoomable=true %}
    </div>
	<div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-odor/map4.png" class="img-fluid rounded" zoomable=true %}
    </div>
</div>
<div class="caption">
    Neuron-odour maps representing different odours.
</div> 
<br><br>

---

More information can be found at {% cite tantirigama2017spontaneous %}
<br><br>

