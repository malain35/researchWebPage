+++
abstract = "Light fields are able to capture light rays from a scene arriving at different angles, which allows post-capture rendering applications such as interactive viewpoint selection or refocusing. However, this additional angular information comes at the price of a significant increase of the data volume compared to traditional 2D images. While light field compression is still an ongoing research effort, showing impressive compression gain with the latest coding standard, light fields are in practice often stored on remote servers to avoid consuming unnecessary storage of the user devices. A typical cost-effective solution for light field visualisation is then to render the requested image on the server and transmit the result to the user. Another trivial solution would be to directly send the light field to the user and perform the rendering process directly on the client side to avoid transmission delay. While the latter solution seems instinctively less optimal and is usually discarded in previous work because of occurring long startup delay, we propose a quantitative study to compare both solutions in terms of rate-distortion (RD) performance. A counterintuitive finding of this paper is that accepting a reasonable startup delay (around 1s) can provide a significant improvement of the RD performances."
abstract_short = ""
authors = ["M. Alain", "C. Ozcinar", "A. Smolic"]
date = "2019-11-04"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Conference on Image Processing"
publication_short = "ICIP 2019"
publication_types = ["1"]
selected = false
title = "A Study of Light Field Streaming for Interactive Refocusing"
url_code = ""
url_dataset = ""
url_pdf = "pdf/LF_streaming_study_v1.pdf"
url_project = ""
url_slides = ""
url_video = ""

#[[url_custom]]
#name = "BibTex"
#url = "bib/AlainICIP2018.bib"

#[[url_custom]]
#name = "IEEE Xplore"
#url = "http://ieeexplore.ieee.org/document/6952021/"

[[url_custom]]
name = "V-SENSE"
url = "https://v-sense.scss.tcd.ie/research/light-fields/lf-streaming/"

[header]
image = "headers/LF_streaming_scenario_AB-732x641.png"
caption = ""

+++


<h2>Additional results</h2>
Detailed RD results for the Lytro Illum, Stanford, and Technicolor datasets using a full synthetic aperture are shown below.
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="0" align="center">
<tbody>
<tr>
<td></td>
<td>Lytro Illum dataset</td>
<td></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Bee1_fsa.png"><img class="alignnone size-medium wp-image-3436" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Bee1_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Bee2_fsa.png"><img class="alignnone size-medium wp-image-3437" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Bee2_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Bikes_fsa.png"><img class="alignnone size-medium wp-image-3438" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Bikes_fsa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Friends_fsa.png"><img class="alignnone size-medium wp-image-3414" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Friends_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Vespa_fsa.png"><img class="alignnone size-medium wp-image-3434" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Vespa_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Cherrytree_fsa.png"><img class="alignnone size-medium wp-image-3440" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Cherrytree_fsa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td></td>
<td>Stanford dataset</td>
<td></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_fsa.png"><img class="alignnone size-medium wp-image-3443" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_fsa.png"><img class="alignnone size-medium wp-image-3447" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_fsa.png"><img class="alignnone size-medium wp-image-3417" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_fsa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_fsa.png"><img class="alignnone size-medium wp-image-3421" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_fsa.png"><img class="alignnone size-medium wp-image-3426" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_fsa.png"><img class="alignnone size-medium wp-image-3430" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_fsa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td></td>
<td>Techicolor dataset</td>
<td></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Automaton_fsa.png"><img class="alignnone size-medium wp-image-3435" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Automaton_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Birthday_fsa.png"><img class="alignnone size-medium wp-image-3439" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Birthday_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Painter_fsa.png"><img class="alignnone size-medium wp-image-3423" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Painter_fsa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Theater_fsa.png"><img class="alignnone size-medium wp-image-3432" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Theater_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Train_fsa.png"><img class="alignnone size-medium wp-image-3433" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Train_fsa-300x225.png" alt="" width="300" height="225"></a></td>
<td></td>
</tr>
</tbody>
</table>
Detailed RD results for the Stanford dataset using different synthetic aperture sizes are shown below.
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="0" align="center">
<tbody>
<tr>
<td></td>
<td>5x5 synthetic aperture</td>
<td></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_5x5.png"><img class="alignnone size-medium wp-image-3441" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_5x5-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_5x5.png"><img class="alignnone size-medium wp-image-3445" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_5x5-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_5x5.png"><img class="alignnone size-medium wp-image-3415" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_5x5-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_5x5.png"><img class="alignnone size-medium wp-image-3419" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_5x5-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_5x5.png"><img class="alignnone size-medium wp-image-3424" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_5x5-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_5x5.png"><img class="alignnone size-medium wp-image-3428" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_5x5-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td></td>
<td>9x9 synthetic aperture</td>
<td></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_9x9.png"><img class="alignnone size-medium wp-image-3442" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_9x9-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_9x9.png"><img class="alignnone size-medium wp-image-3446" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_9x9-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_9x9.png"><img class="alignnone size-medium wp-image-3416" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_9x9-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_9x9.png"><img class="alignnone size-medium wp-image-3420" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_9x9-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_9x9.png"><img class="alignnone size-medium wp-image-3425" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_9x9-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_9x9.png"><img class="alignnone size-medium wp-image-3429" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_9x9-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td></td>
<td>Dynamic synthetic aperture</td>
<td></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_isa.png"><img class="alignnone size-medium wp-image-3444" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Chess_isa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_isa.png"><img class="alignnone size-medium wp-image-3448" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/Eucalyptus_isa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_isa.png"><img class="alignnone size-medium wp-image-3418" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoBulldozer_isa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_isa.png"><img class="alignnone size-medium wp-image-3422" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/LegoKnights_isa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_isa.png"><img class="alignnone size-medium wp-image-3427" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsLA_isa-300x225.png" alt="" width="300" height="225"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_isa.png"><img class="alignnone size-medium wp-image-3431" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2019/02/TarotsSA_isa-300x225.png" alt="" width="300" height="225"></a></td>
</tr>
</tbody>
</table>
