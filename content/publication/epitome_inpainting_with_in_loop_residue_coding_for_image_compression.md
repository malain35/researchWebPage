+++
abstract = "This paper describes a novel image coding scheme based on epitome inpainting. An epitome containing a factorized texture representation of the image is first coded and transmitted. The decoded epitome is then inpainted by propagating its structure and texture with extended H.264 Intra directional prediction modes and advanced neighbor embedding methods. The blocks to be inpainted are processed according to an adaptive scanning order which adapts to the image content and gives a higher priority to the blocks having strong structures. The inpainting step has been incorporated in the coding loop of an H.264 encoder, leading to a bitrate saving of up to 48.12% with respect to H.264 intra."
abstract_short = ""
authors = ["C. Cherigui", "M. Alain", "C. Guillemot", "D. Thoreau", "P. Guillotel"]
date = "2014-10-27"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Conference on Image Processing"
publication_short = "ICIP 2014"
publication_types = ["1"]
selected = false
title = "Epitome inpainting with in-loop residue coding for image compression"
url_code = ""
url_dataset = ""
url_pdf = "pdf/Adaptive_scanning_ICIP_2014_final_embedded_font.pdf"
url_project = ""
url_slides = ""
url_video = ""

#[[url_custom]]
#name = "BibTex"
#url = "bib/CheriguiICIP2014.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "http://ieeexplore.ieee.org/document/7026129/"

[[url_custom]]
name = "INRIA"
url = "https://www.irisa.fr/temics/demos/epitomeInpaintingImageCoding/epitomeInpaintingImageCoding.html"

[header]
image = ""
caption = ""

+++



## Context and Goal

Image/video compression standards such as JPEG, H.264, and more recently HEVC, achieve state-of-the-art compression performances. However, modern image formats call for improved coding performances. Independently from the standard image/video compression techniques emerged the concept of epitome, first presented by Jojic et al., which is defined as a condensed representation of an image or video containing the essence of its textural properties.  
In this work, we propose a novel image coding scheme exploiting the epitome concept.

## Approach

The main steps of the proposed coding scheme are depicted in Fig. 1.  

First, an epitome consisting of texture pieces from the input image is generated and encoded. More explanations on the epitome generation are available [here](https://www.scss.tcd.ie/~alainm/publication/clustering_based_methods_for_fast_epitome_generation/) or in the papers listed [at the end of this page.](#references)

Second, the epitome is decoded and used to predict the missing non-epitome blocks in an inpainting fashion, which implies changing the scanning order of the blocks in the encoder. An adaptive scanning order is thus used, based on the priority order proposed by criminisi et al. for object removal, adapted here to fit with the block structure of the encoder. Blocks surrounded by strong linear structures and a larger number of reliable pixels are assigned the highest priority and processed first. The inpainting of the epitome is performed by propagating texture and structure using extended multi-directional H.264 Intra prediction modes in competition with extra modes based on block matching and weighted template matching techniques.  

Finally, the best mode is selected using an RDO criterion and once the prediction obtained, the residue of the block is computed, transformed, quantized and entropy coded with the H.264 encoding tools. At the decoder side the residue is obtained by inverse transform and dequantization. The block is immediately reconstructed by adding the decoded residue to the prediction. The reconstructed block is then available in the causal part of the image and the new front line is taken into account when computing the new filling order for the inpainting of the next block.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/eptmInpaint_files/scheme_illustrated.png" caption="Proposed compression scheme based on epitome inpainting and in-loop residue coding." >}}

## Experimental Results

To validate the approach, the inpainting step has been integrated in an H.264 codec with the block size set to 8x8. Objective assessments of the method were obtained using the Bjontegaard metric at low (Quantization parameter (QP) = 26, 31, 36, 41) and high bitrates (QP = 16, 21, 26, 31). Note that in the following results, the measured bitstream does take into account both the epitome texture and the non-epitome block residue bitstreams. The method was tested on a set of four images: Barbara, Building, Spincalendar and Wool.

In the videos below, we show the comparison between the usual raster scanning order and the adaptive scanning order of the proposed method for the Barbara and Spincalendar images.  
In each video, the raster scan can be seen on the left and the adaptive scan on the right. The top row represents the encoding at high bitrate (QP=16) while the bottom row represents the encoding at low bitrate (QP=41). One can thus notice the changes in the adaptive scan depending on the image quality.  
Note that we show here the prediction images.  
We recommend Firefox or Chrome browsers to play the videos.

<video width="512" height="512" controls=""><source src="https://www.scss.tcd.ie/~alainm/img/eptmInpaint_files/barbara_scan4_step4_1024x1024.webm" type="video/webm"> Your browser does not support the video tag.</video>

<td><video width="512" height="512" controls=""><source src="https://www.scss.tcd.ie/~alainm/img/eptmInpaint_files/spin_demo.webm" type="video/webm"> Your browser does not support the video tag.</video>

We show in Table 1 the RD performances against H.264, compared to a modified H.264 codec integrating the additional prediction modes used in the proposed method.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 1 - Comparison between the inpainting scheme integrated with neighbor embedding and H.264 intra modes with additional neighbor embedding</caption>

<tbody>

<tr>
<td></td>
<td colspan="4">Low bitrates</td>

<td colspan="4">High bitrates</td>

</tr>

<tr>
<td></td>
<td colspan="2">Raster scan</td>

<td colspan="2">Adapt. scan</td>

<td colspan="2">Raster scan</td>

<td colspan="2">Adapt. scan</td>

</tr>

<tr>
<td></td>
<td>dB</td>

<td>% rate</td>

<td>dB</td>

<td>% rate</td>

<td>dB</td>

<td>% rate</td>

<td>dB</td>

<td>% rate</td>

</tr>

<tr>

<td>Barbara</td>

<td>1.19</td>

<td>-17.07</td>

<td>1.13</td>

<td>-16.16</td>

<td>0.92</td>

<td>-10.53</td>

<td>0.92</td>

<td>-10.58</td>

</tr>

<tr>

<td>Building</td>

<td>4.23</td>

<td>-46.78</td>

<td>4.40</td>

<td>-48.12</td>

<td>4.32</td>

<td>-32.80</td>

<td>4.48</td>

<td>-33.89</td>

</tr>

<tr>

<td>Spincalendar</td>

<td>2.87</td>

<td>-37.59</td>

<td>3.15</td>

<td>-39.99</td>

<td>2.64</td>

<td>-26.83</td>

<td>2.97</td>

<td>-29.92</td>

</tr>

<tr>

<td>Wool</td>

<td>2.28</td>

<td>-32.73</td>

<td>2.33</td>

<td>-33.39</td>

<td>1.76</td>

<td>-18.93</td>

<td>1.81</td>

<td>-19.39</td>

</tr>

<tr>

<th>Average</th>

<th>2.64</th>

<th>-33.54</th>

<th>2.75</th>

<th>-34.42</th>

<th>2.41</th>

<th>-22.27</th>

<th>2.54</th>

<th>-23.44</th>

</tr>

</tbody>

</table>

## References

*   Safa Cherigui, [Christine Guillemot](http://www.irisa.fr/temics/staff/guillemot/), [Dominique Thoreau](http://www.technicolor.com/en/dominique-thoreau), [Philippe Guilltotel](http://www.technicolor.com/en/philippe-guillotel) and [Patrick Perez](http://www.technicolor.com/en/patrick-perez), **Epitome-based image compression using translational sub-pel mapping**, _MMSP 2011._ [[PDF]](https://hal.inria.fr/hal-00994418/document)
*   Antonio Criminisi, Patrick Perez, Kentaro Toyama, **Region filling and object removal by exemplar-based inpainting**, _IEEE TIP 2004._ [[PDF]](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/criminisi_tip2004.pdf) [[Web]](https://www.microsoft.com/en-us/research/publication/region-filling-and-object-removal-by-exemplar-based-inpainting/)

