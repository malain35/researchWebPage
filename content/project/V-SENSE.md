+++
# Date this page was created.
date = "2016-04-27"

# Project title.
title = "V-SENSE"

# Project summary to display on homepage.
summary = "Extending Visual Sensation through Image-Based Visual Computing"

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = "headers/VS-Font-FINAL.jpg"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["V-SENSE"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
#image = "headers/Cherry_tree_2_side_by_side_focus.png"
image = "headers/VS-Font-FINAL.jpg"
caption = ""

+++

## Extending Visual Sensation through Image-Based Visual Computing

Since September 2016, I am a research fellow in the [V-SENSE project](https://v-sense.scss.tcd.ie/), lead by Professor [Aljosa Smolic](https://www.scss.tcd.ie/Aljosa.Smolic/).
V-SENSE is a team of 20+ researchers (half postdocs half PhDs) in Visual Computing at the intersection of Computer Vision, Computer Graphics and Media Signal Processing.
My research is focused on light field imaging technologies, investigating novel methods for light field denoising, scene reconstruction from light field, and light field rendering.

## Light fields imaging technologies

Light fields capture all light rays passing through a given volume of space.
Compared to traditional 2D imaging systems which capture the spatial intensity of the light rays, the 4D light fields also contain the angular direction of light rays.
This additional information allows for multiple applications in different research areas such as image processing, computer vision, and computer graphics, including (but not limited to) the reconstruction of the 3D geometry of a scene, creating new images from virtual point of view, or changing the focus of an image after it is captured.
Light fields are also a growing topic of interest in the VR/AR community.

Below is an example of a light field captured with a Lytro Illum camera, which allows for refocusing and changing the perspective.

<iframe width='809' height='540' src='https://www.scss.tcd.ie/~alainm/vid/Lytro_example.mp4' frameborder='0' allowfullscreen scrolling='no'></iframe>


## Related publications

* [Fast and Accurate Optical Flow based Depth Map Estimation from Light Fields]({{< relref "Fast and Accurate Optical Flow based Depth Map Estimation from Light Fields.md" >}})
* [Light Field Denoising by Sparse 5D Transform Domain Collaborative Filtering]({{< relref "Light_Field_Denoising_by_Sparse_5D_Transform_Domain_Collaborative_Filtering.md" >}})
