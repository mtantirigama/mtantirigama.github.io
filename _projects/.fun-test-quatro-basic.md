---
layout: page
title: fun test quatro basics
description: md from quatro basics
img: assets/img/prof_pic_color.jpg
importance: 1
category: fun
related_publications: true
---

# Quarto Basics


- [Polar Axis](#polar-axis)
  - [With echo on to show code only for this
    cell](#with-echo-on-to-show-code-only-for-this-cell)
- [subplot with sub-captions](#subplot-with-sub-captions)

## Polar Axis

For a demonstration of a line plot on a polar axis, see
<a href="#fig-polar" class="quarto-xref">Figure 1</a>.

![](/assets/img/quatro/fig-polar-output-1.png)

### With echo on to show code only for this cell

``` python
theta = 5 * np.pi * r
fig, ax = plt.subplots(
  subplot_kw = {'projection': 'polar'} 
)
ax.plot(theta, r)
ax.set_rticks([0.5, 1, 1.5, 2])
ax.grid(True)
plt.show()
```

![](/assets/img/quatro/cell-3-output-1.png)

## subplot with sub-captions

``` python
import matplotlib.pyplot as plt
plt.plot([1,23,2,4])
plt.show()

plt.plot([8,65,23,90])
plt.show()
```

<div class="cell-output cell-output-display column-page">

<img
src="/assets/img/quatro/fig-gapminder-output-1.png"
data-ref-parent="fig-gapminder" />

</div>

<div class="cell-output cell-output-display column-page">

<img
src="/assets/img/quatro/fig-gapminder-output-2.png"
data-ref-parent="fig-gapminder" />

</div>

> [!NOTE]
>
> Note that there are five types of callouts
> including:‘note’,‘tip’,‘warning’,‘caution’,‘important’.

> [!TIP]
>
> an example of ‘tip’.

![Elephant](/assets/img/prof_pic_color.jpg)

<img src="/assets/img/prof_pic2.jpg" data-ref-parent="fig-me" />

<img src="/assets/img/prof_pic_color.jpg" data-ref-parent="fig-me" />
<iframe width="560" height="315" src="https://www.youtube.com/embed/afql9dbjcq0?si=v3vZUdE_b1wHGk6V" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>

[![](/assets/img/prof_pic_color.jpg)](https://en.wikipedia.org/wiki/Elephant)

