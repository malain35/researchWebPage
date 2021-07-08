+++
abstract = "In this paper, we propose a spatial super-resolution method for light fields, which combines the SR-BM3D single image super-resolution filter and the recently introduced LFBM5D light field denoising filter. The proposed algorithm iteratively alternates between an LFBM5D filtering step and a back-projection step. The LFBM5D filter creates disparity compensated 4D patches which are then stacked together with similar 4D patches along a 5th dimension. The 5D patches are then filtered in the 5D transform domain to enforce a sparse coding of the high-resolution light field, which is a powerful prior to solve the ill-posed super-resolution problem. The back-projection step then impose the consistency between the known low-resolution light field and the-high resolution estimate. We further improve this step by using image guided filtering to remove ringing artifacts. Results show that significant improvement can be achieved compared to state-of-the-art methods, for both light fields captured with a lenslet camera or a gantry."
abstract_short = ""
authors = ["M. Alain", "A. Smolic"]
date = "2018-06-07"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Conference on Image Processing"
publication_short = "ICIP 2018"
publication_types = ["1"]
selected = true
title = "Light Field Super-Resolution via LFBM5D Sparse Coding"
url_code = ""
url_dataset = ""
url_pdf = "pdf/LFBM5D_SR.pdf"
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
url = "https://v-sense.scss.tcd.ie/?p=1551"

[header]
image = "headers/comparison_before_after_SR.png"
caption = ""

+++

<h2>Implementation</h2>
The MATLAB/C/C++ source code is now available on <a href="https://github.com/malain35/LFBM5D/tree/SR">github</a> !

<h2>Additional results</h2>
Visual results complementing the paper are shown below.
We then show in Tables 1 and 2 <a href="#avgres">the average results</a> presented in the paper. The corresponding <a href="#detres">detailed results</a> are shown in Table 3 and 4.

<h3>Lytro Illum dataset</h3>
We use in our experiments a Lytro Illum dataset consisting of light fields taken from the <a href="https://mmspg.epfl.ch/EPFL-light-field-image-dataset">EPFL</a> and the <a href="https://www.irisa.fr/temics/demos/lightField/CLIM/DataSoftware.html">INRIA</a> datasets.
These light fields have been further processed with the V-SENSE enhancement pipeline described <a href="https://v-sense.scss.tcd.ie/?p=1548">here</a>.

<h3 id="visres">Visual results</h3>
We show in videos below (click on an image to start a video) side by side comparisons of low-resolution (uspampled with a bicubic filter) and super-resolved light fields for different scaling factors &alpha;. On the top left corner of each video is highlighted the sub-aperture image being displayed. Note that some videos may exhibit encoding artifacts.

<table style="text-align: center; width: 100%;" border="0" cellspacing="2" cellpadding="2" align="center">
<tbody>
<tr>
<td></td>
<td>&alpha;=2</td>
<td>&alpha;=3</td>
<td>&alpha;=4</td>
</tr>
<tr>
<td>Chess</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Chess_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-20.png" alt="&alpha;=2" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Chess_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-21.png" alt="&alpha;=3" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Chess_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-24.png" alt="&alpha;=4" width="100" height="100" /></a></td>
</tr>
<tr>
<td>Lego Bulldozer</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoBulldozer_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-15.png" alt="&alpha;=2" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoBulldozer_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-16.png" alt="&alpha;=3" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoBulldozer_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-25.png" alt="&alpha;=4" width="100" height="100" /></a></td>
</tr>
<tr>
<td>Lego Knights</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoKnights_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-17.png" alt="&alpha;=2" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoKnights_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-18.png" alt="&alpha;=3" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoKnights_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-26.png" alt="&alpha;=4" width="100" height="100" /></a></td>
</tr>
<tr>
<td>Tarot Cards and Crystal Ball (Large Angle)</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_TarotsCardsandCrystalBallLA_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-19.png" alt="&alpha;=2" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_TarotsCardsandCrystalBallLA_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-28.png" alt="&alpha;=3" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_TarotCardsandCrystalBallLA_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-27.png" alt="&alpha;=4" width="100" height="100" /></a></td>
</tr>
<tr>
<td>Bee 2</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bee2_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-300x209.png" alt="&alpha;=2" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bee2_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-1.png" alt="&alpha;=3" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bee2_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-11.png" alt="&alpha;=4" width="100" height="70" /></a></td>
</tr>
<tr>
<td>Bikes</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bikes_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-3-300x209.png" alt="&alpha;=2" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bikes_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-4.png" alt="&alpha;=3" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bikes_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-12.png" alt="&alpha;=4" width="100" height="70" /></a></td>
</tr>
<tr>
<td>Danger de mort</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_DangerDeMort_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-6-300x209.png" alt="&alpha;=2" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_DangerDeMort_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-7.png" alt="&alpha;=3" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_DangerDeMort_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-13.png" alt="&alpha;=4" width="100" height="70" /></a></td>
</tr>
<tr>
<td>Vespa</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Vespa_x2.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-8-300x209.png" alt="&alpha;=2" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Vespa_x3.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-9.png" alt="&alpha;=3" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Vespa_x4.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-14.png" alt="&alpha;=4" width="100" height="70" /></a></td>
</tr>
</tbody>
</table>
Below, we show results for &alpha;=4 without (left) and with (right) the light field guided filtering described in section 2.2 of the paper to improve back-projection (click on an image to start a video).
<table style="text-align: center; width: 100%;" border="0" cellspacing="2" cellpadding="2" align="center">
<tbody>
<tr>
<td>Chess</td>
<td>Lego Knights</td>
<td>Bikes</td>
<td>Vespa</td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Chess_x4GBP.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-22.png" alt="Chess" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_LegoKnights_x4GBP.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-29.png" alt="Lego Knights" width="100" height="100" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bikes_x4GBP.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-5.png" alt="Bikes" width="100" height="70" /></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Vespa_x4GBP.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/SAI_00_00-10.png" alt="Vespa" width="100" height="70" /></a></td>
</tr>
</tbody>
</table>
<h3 id="avgres">Average PSNR results</h3>
<!-- The &Delta;PSNR lines in Tables 1 and 2 correspond to the PSNR gap between the proposed approach and the best state-of-the-art method. -->
Values highlighted in bold and italic correspond to the best and second best performing methods respectively for a given magnification factor.
<table style="text-align: center; width: 100%;" border="1" cellspacing="2" cellpadding="2" align="center"><caption><b>Table 1 - </b> Average SR performances in PSNR for the Lytro Illum dataset.</caption>
<tbody>
<tr>
<td></td>
<td>&alpha;=2</td>
<td>&alpha;=3</td>
<td>&alpha;=4</td>
</tr>
<tr>
<td>Bicubic</td>
<td>27.78</td>
<td>26.08</td>
<td>24.62</td>
</tr>
<tr>
<td>SR-BM3D</td>
<td><i>30.21</i></td>
<td>28.45</td>
<td>26.58</td>
</tr>
<tr>
<td>BM+PCA+RR</td>
<td>29.95</td>
<td>28.55</td>
<td><i>27.08</i></td>
</tr>
<tr>
<td>GB</td>
<td>29.80</td>
<td><b>28.65</b></td>
<td><b>27.45</b></td>
</tr>
<tr>
<td>SR-LFBM5D 1st step</td>
<td>30.17</td>
<td><i>28.62</i></td>
<td>26.87</td>
</tr>
<tr>
<td>SR-LFBM5D 2nd step</td>
<td><b>30.25</b></td>
<td>28.60</td>
<td>26.82</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" border="1" cellspacing="2" cellpadding="2" align="center"><caption><b>Table 2 - </b> Average SR performances in PSNR for the Stanford dataset.</caption>
<tbody>
<tr>
<td></td>
<td>&alpha;=2</td>
<td>&alpha;=3</td>
<td>&alpha;=4</td>
</tr>
<tr>
<td>Bicubic</td>
<td>29.00</td>
<td>26.81</td>
<td>25.06</td>
</tr>
<tr>
<td>SR-BM3D</td>
<td>34.10</td>
<td>30.90</td>
<td>28.00</td>
</tr>
<tr>
<td>BM+PCA+RR</td>
<td>32.81</td>
<td>30.85</td>
<td>28.73</td>
</tr>
<tr>
<td>GB</td>
<td>33.01</td>
<td>31.42</td>
<td><b>29.44</b></td>
</tr>
<tr>
<td>SR-LFBM5D 1st step</td>
<td><i>34.15</i></td>
<td><b>31.81</b></td>
<td><i>29.10</i></td>
</tr>
<tr>
<td>SR-LFBM5D 2nd step</td>
<td><b>34.27</b></td>
<td><i>31.77</i></td>
<td>29.02</td>
</tr>
</tbody>
</table>
<h3 id="detres">Detailed PSNR results</h3>
<table style="text-align: center; width: 100%;" border="1" cellspacing="2" cellpadding="2" align="center"><caption><b>Table 3 - </b> SR performances in PSNR for each light field in the Lytro Illum dataset.</caption>
<tbody>
<tr>
<td></td>
<td>Ankylosorus &amp; Dipplodocus 1</td>
<td>Bee 1</td>
<td>Bee 2</td>
<td>Bikes</td>
<td>Chez Edgar</td>
<td>Danger de Mort</td>
<td>Friends 1</td>
<td>Fruits</td>
<td>Magnets 1</td>
<td>Posts</td>
<td>Rose</td>
<td>Vespa</td>
</tr>
<tr>
<td colspan="13">Bicubic</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>33.5414</td>
<td>27.0979</td>
<td>27.5808</td>
<td>26.2794</td>
<td>22.3877</td>
<td>24.3675</td>
<td>28.713</td>
<td>26.0159</td>
<td>31.0621</td>
<td>30.4165</td>
<td>28.5095</td>
<td>27.3734</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>31.5025</td>
<td>25.4013</td>
<td>25.9392</td>
<td>24.5069</td>
<td>21.1371</td>
<td>22.8849</td>
<td>26.589</td>
<td>24.3747</td>
<td>29.0306</td>
<td>29.2154</td>
<td>26.8529</td>
<td>25.5526</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>29.7729</td>
<td>23.8938</td>
<td>24.4516</td>
<td>22.9869</td>
<td>20.0919</td>
<td>21.7029</td>
<td>24.769</td>
<td>22.9985</td>
<td>27.2962</td>
<td>28.0506</td>
<td>25.4262</td>
<td>24.0135</td>
</tr>
<tr>
<td colspan="13">SR-BM3D</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>36.075</td>
<td>29.023</td>
<td>29.346</td>
<td>30.058</td>
<td>24.220</td>
<td>27.101</td>
<td>32.185</td>
<td>28.791</td>
<td>33.858</td>
<td>30.958</td>
<td>30.597</td>
<td>30.354</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>34.207</td>
<td>27.892</td>
<td>28.265</td>
<td>27.978</td>
<td>22.433</td>
<td>24.979</td>
<td>30.423</td>
<td>26.827</td>
<td>31.500</td>
<td>29.667</td>
<td>28.733</td>
<td>28.534</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>32.477</td>
<td>26.421</td>
<td>26.959</td>
<td>25.369</td>
<td>20.908</td>
<td>22.756</td>
<td>28.256</td>
<td>24.748</td>
<td>29.300</td>
<td>28.299</td>
<td>26.801</td>
<td>26.698</td>
</tr>
<tr>
<td colspan="13">BM+PCA+RR</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>35.6127</td>
<td>28.7435</td>
<td>29.0858</td>
<td>29.5911</td>
<td>24.2046</td>
<td>26.8869</td>
<td>31.8674</td>
<td>28.6242</td>
<td>33.4409</td>
<td>30.8375</td>
<td>30.4213</td>
<td>30.1102</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>34.3607</td>
<td>27.6675</td>
<td>28.225</td>
<td>27.8739</td>
<td>22.7327</td>
<td>25.2586</td>
<td>30.4348</td>
<td>27.1949</td>
<td>31.5474</td>
<td>29.704</td>
<td>28.9552</td>
<td>28.6078</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>32.9217</td>
<td>26.4726</td>
<td>27.1327</td>
<td>26.0074</td>
<td>21.4623</td>
<td>23.7469</td>
<td>28.7222</td>
<td>25.6303</td>
<td>29.7057</td>
<td>28.5436</td>
<td>27.481</td>
<td>27.1216</td>
</tr>
<tr>
<td colspan="13">GB</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>35.7291</td>
<td>28.7144</td>
<td>29.159</td>
<td>29.329</td>
<td>23.753</td>
<td>26.618</td>
<td>31.629</td>
<td>28.249</td>
<td>33.353</td>
<td>30.9148</td>
<td>30.292</td>
<td>29.918</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>34.606</td>
<td>27.774</td>
<td>28.395</td>
<td>28.073</td>
<td>22.644</td>
<td>25.356</td>
<td>30.531</td>
<td>27.159</td>
<td>31.672</td>
<td>29.781</td>
<td>28.976</td>
<td>28.781</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>33.441</td>
<td>26.757</td>
<td>27.588</td>
<td>26.643</td>
<td>21.536</td>
<td>24.126</td>
<td>29.114</td>
<td>26.108</td>
<td>29.991</td>
<td>28.627</td>
<td>27.793</td>
<td>27.619</td>
</tr>
<tr>
<td colspan="13">SR-LFBM5D 1st step</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>36.044</td>
<td>28.992</td>
<td>29.303</td>
<td>29.977</td>
<td>24.222</td>
<td>27.059</td>
<td>32.136</td>
<td>28.714</td>
<td>33.840</td>
<td>30.917</td>
<td>30.495</td>
<td>30.326</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>34.559</td>
<td>27.921</td>
<td>28.366</td>
<td>28.127</td>
<td>22.459</td>
<td>25.171</td>
<td>30.529</td>
<td>27.139</td>
<td>31.586</td>
<td>29.767</td>
<td>29.039</td>
<td>28.756</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>33.068</td>
<td>26.587</td>
<td>27.203</td>
<td>25.678</td>
<td>20.977</td>
<td>22.794</td>
<td>28.649</td>
<td>25.246</td>
<td>29.415</td>
<td>28.456</td>
<td>27.262</td>
<td>27.133</td>
</tr>
<tr>
<td colspan="13">SR-LFBM5D 2nd step</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>36.123</td>
<td>29.037</td>
<td>29.350</td>
<td>30.098</td>
<td>24.282</td>
<td>27.144</td>
<td>32.242</td>
<td>28.816</td>
<td>33.899</td>
<td>30.966</td>
<td>30.602</td>
<td>30.425</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>34.532</td>
<td>27.908</td>
<td>28.348</td>
<td>28.115</td>
<td>22.439</td>
<td>25.133</td>
<td>30.513</td>
<td>27.106</td>
<td>31.573</td>
<td>29.768</td>
<td>29.007</td>
<td>28.731</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>33.032</td>
<td>26.561</td>
<td>27.170</td>
<td>25.614</td>
<td>20.909</td>
<td>22.650</td>
<td>28.595</td>
<td>25.161</td>
<td>29.379</td>
<td>28.447</td>
<td>27.201</td>
<td>27.074</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" border="1" cellspacing="2" cellpadding="2" align="center"><caption><b>Table 4 - </b> SR performances in PSNR for each light field in the Stanford dataset.</caption>
<tbody>
<tr>
<td></td>
<td>Amethyst</td>
<td>Bracelet</td>
<td>Chess</td>
<td>Eucalyptus Flowers</td>
<td>Jelly beans</td>
<td>Lego Bulldozer</td>
<td>Lego Knights</td>
<td>Lego Truck</td>
<td>Tarot Cards and Crystal Ball (Large Angle)</td>
<td>Tarot Cards and Crystal Ball (Small Angle)</td>
<td>The Stanford Bunny</td>
<td>Treasure Chest</td>
</tr>
<tr>
<td colspan="13">Bicubic</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>27.9143</td>
<td>26.3944</td>
<td>31.0063</td>
<td>23.3153</td>
<td>41.5464</td>
<td>26.9215</td>
<td>28.5825</td>
<td>27.7637</td>
<td>27.0215</td>
<td>27.103</td>
<td>36.0681</td>
<td>24.3827</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>25.846</td>
<td>24.1524</td>
<td>28.707</td>
<td>22.1331</td>
<td>38.0155</td>
<td>24.7319</td>
<td>26.3982</td>
<td>25.8623</td>
<td>25.2307</td>
<td>24.8391</td>
<td>32.8963</td>
<td>22.9615</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>24.1607</td>
<td>22.3826</td>
<td>26.8413</td>
<td>21.2074</td>
<td>35.4326</td>
<td>22.9613</td>
<td>24.5788</td>
<td>24.2874</td>
<td>23.5296</td>
<td>23.1016</td>
<td>30.4554</td>
<td>21.745</td>
</tr>
<tr>
<td colspan="13">SR-BM3D</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>32.591</td>
<td>34.325</td>
<td>37.250</td>
<td>26.424</td>
<td>45.191</td>
<td>32.029</td>
<td>34.014</td>
<td>31.820</td>
<td>32.241</td>
<td>33.764</td>
<td>41.051</td>
<td>28.487</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>29.935</td>
<td>29.172</td>
<td>33.646</td>
<td>23.929</td>
<td>42.740</td>
<td>29.198</td>
<td>30.944</td>
<td>28.929</td>
<td>29.048</td>
<td>28.878</td>
<td>38.889</td>
<td>25.505</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>27.491</td>
<td>25.111</td>
<td>30.247</td>
<td>22.269</td>
<td>39.682</td>
<td>26.305</td>
<td>28.053</td>
<td>26.103</td>
<td>26.087</td>
<td>25.339</td>
<td>36.061</td>
<td>23.264</td>
</tr>
<tr>
<td colspan="13">BM+PCA+RR</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>32.1632</td>
<td>32.8753</td>
<td>36.1938</td>
<td>26.2293</td>
<td>43.3373</td>
<td>30.5675</td>
<td>32.8232</td>
<td>31.4071</td>
<td>28.4677</td>
<td>31.6728</td>
<td>39.7559</td>
<td>28.1899</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>30.281</td>
<td>30.260</td>
<td>33.903</td>
<td>24.775</td>
<td>41.575</td>
<td>28.482</td>
<td>30.898</td>
<td>29.497</td>
<td>26.363</td>
<td>29.435</td>
<td>38.600</td>
<td>26.169</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>28.428</td>
<td>26.799</td>
<td>31.713</td>
<td>23.344</td>
<td>39.239</td>
<td>26.367</td>
<td>28.695</td>
<td>27.502</td>
<td>24.485</td>
<td>27.127</td>
<td>36.452</td>
<td>24.578</td>
</tr>
<tr>
<td colspan="13">GB</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>32.164</td>
<td>32.164</td>
<td>35.715</td>
<td>25.529</td>
<td>45.301</td>
<td>30.928</td>
<td>32.768</td>
<td>30.968</td>
<td>31.457</td>
<td>30.939</td>
<td>41.017</td>
<td>27.192</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>30.245</td>
<td>30.34</td>
<td>34.136</td>
<td>24.595</td>
<td>43.182</td>
<td>29.293</td>
<td>31.475</td>
<td>29.549</td>
<td>29.298</td>
<td>29.620</td>
<td>39.330</td>
<td>25.976</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>29.127</td>
<td>28.16</td>
<td>32.636</td>
<td>24.012</td>
<td>40.835</td>
<td>27.828</td>
<td>29.995</td>
<td>28.007</td>
<td>21.534</td>
<td>28.148</td>
<td>37.816</td>
<td>25.203</td>
</tr>
<tr>
<td colspan="13">SR-LFBM5D 1st step</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>32.620</td>
<td>34.214</td>
<td>37.455</td>
<td>26.450</td>
<td>45.396</td>
<td>32.007</td>
<td>34.210</td>
<td>31.896</td>
<td>32.278</td>
<td>33.673</td>
<td>41.109</td>
<td>28.514</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>30.440</td>
<td>30.535</td>
<td>35.242</td>
<td>24.653</td>
<td>43.099</td>
<td>29.804</td>
<td>32.467</td>
<td>29.949</td>
<td>30.077</td>
<td>29.863</td>
<td>39.412</td>
<td>26.141</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>28.125</td>
<td>26.351</td>
<td>31.670</td>
<td>22.838</td>
<td>40.689</td>
<td>27.241</td>
<td>29.767</td>
<td>27.510</td>
<td>26.837</td>
<td>26.724</td>
<td>37.157</td>
<td>24.324</td>
</tr>
<tr>
<td colspan="13">SR-LFBM5D 2nd step</td>
</tr>
<tr>
<td>&alpha;=2</td>
<td>32.775</td>
<td>34.508</td>
<td>37.567</td>
<td>26.584</td>
<td>45.261</td>
<td>32.125</td>
<td>34.312</td>
<td>31.982</td>
<td>32.445</td>
<td>33.902</td>
<td>41.172</td>
<td>28.659</td>
</tr>
<tr>
<td>&alpha;=3</td>
<td>30.400</td>
<td>30.477</td>
<td>35.206</td>
<td>24.629</td>
<td>43.032</td>
<td>29.769</td>
<td>32.427</td>
<td>29.923</td>
<td>30.046</td>
<td>29.811</td>
<td>39.385</td>
<td>26.112</td>
</tr>
<tr>
<td>&alpha;=4</td>
<td>28.046</td>
<td>26.209</td>
<td>31.618</td>
<td>22.754</td>
<td>40.626</td>
<td>27.152</td>
<td>29.707</td>
<td>27.463</td>
<td>26.738</td>
<td>26.614</td>
<td>37.073</td>
<td>24.236</td>
</tr>
</tbody>
</table>

