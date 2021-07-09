+++
abstract = "In this paper, we propose to extend the state-of-the-art BM3D image denoising filter to light fields, and we denote our method LFBM5D. We take full advantage of the 4D nature of light fields by creating disparity compensated 4D patches which are then stacked together with similar 4D patches along a 5th dimension. We then filter these 5D patches in the 5D transform domain, obtained by cascading a 2D spatial transform, a 2D angular transform, and a 1D transform applied along the similarities. Furthermore, we propose to use the shape-adaptive DCT as the 2D angular transform to be robust to occlusions. Results show a significant improvement in synthetic noise removal compared to state-of-the-art methods, for both light fields captured with a lenslet camera or a gantry. Experiments on Lytro Illum camera noise removal also demonstrate a clear improvement of the light field quality."
abstract_short = ""
authors = ["M. Alain", "A. Smolic"]
date = "2017-10-16"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Workshop on Multimedia Signal Processing"
publication_short = "MMSP 2017"
publication_types = ["1"]
selected = false
title = "Light Field Denoising by Sparse 5D Transform Domain Collaborative Filtering"
url_code = ""
url_dataset = ""
url_pdf = "pdf/LFBM5D_MMSP_camera_ready.pdf"
url_project = ""
url_slides = ""
url_video = ""

[[url_custom]]
name = "BibTex"
url = "bib/AlainMMSP2018.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "https://ieeexplore.ieee.org/document/8122232/"

[[url_custom]]
name = "V-SENSE"
url = "https://v-sense.scss.tcd.ie/?p=893"

[header]
image = "headers/comparison_before_after_dn.png"
caption = ""

+++

This paper was given a <a href="https://www.beds.ac.uk/mmsp2017/awards">Top 10% Paper Award</a> at the MMSP 2017 conference held in Luton, UK.

For the super-resolution extension SR-LFBM5D, see <a href="">this page</a>.

<h2>Implementation</h2>

The C/C++ source code is available on <a href="https://github.com/malain35/LFBM5D">github</a>.

<h2>Additional results</h2>

Visual results complementing the paper are shown below.
We then show in Tables 1 and 2 <a href="#avgres">the average results</a> presented in the paper.
The corresponding <a href="#detres">detailed results</a> are shown in Table 3 and 4.

<h3 id="visres">Visual results</h3>
We show in videos below (click on an image to start a video) side by side comparisons of noisy and de-noised light fields for different noise levels (&sigma; corresponds to the white gaussian noise standard deviation). On the top left corner of each video is highlighted the sub-aperture image being displayed. Note that some videos may exhibit encoding artifacts.

<table style="text-align: center; width: 100%;" border="0" cellspacing="2" cellpadding="2" align="center">
<tbody>
<tr>
<td></td>
<td>&sigma;=10</td>
<td>&sigma;=30</td>
<td>&sigma;=50</td>
</tr>
<tr>
<td>Lego Knights</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_LegoKnights_sigma10.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-300x300.png" alt="&sigma;=10" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_LegoKnights_sigma30.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-1-300x300.png" alt="&sigma;=30" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_LegoKnights_sigma50.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-2-300x300.png" alt="&sigma;=50" width="100" height="100"></a></td>
</tr>
<tr>
<td>Amethyst</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Amethyst_sigma10.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-3-300x300.png" alt="&sigma;=10" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Amethyst_sigma30.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-4-300x300.png" alt="&sigma;=30" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Amethyst_sigma50.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-5-300x300.png" alt="&sigma;=50" width="100" height="100"></a></td>
</tr>
<tr>
<td>Tarot Cards and Crystal Ball (Small Angle)</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_TarotCardsandCrystalBall_SmallAngle_sigma10.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-6-300x300.png" alt="&sigma;=10" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_TarotCardsandCrystalBall_SmallAngle_sigma30.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-7-300x300.png" alt="&sigma;=30" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_TarotCardsandCrystalBall_SmallAngle_sigma50.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_0_0-8-300x300.png" alt="&sigma;=50" width="100" height="100"></a></td>
</tr>
<tr>
<td>Bikes</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Bikes_sigma10.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-300x208.png" alt="&sigma;=10" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Bikes_sigma30.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-1-300x208.png" alt="&sigma;=30" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Bikes_sigma50.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-2-300x208.png" alt="&sigma;=50" width="100" height="70"></a></td>
</tr>
<tr>
<td>Magnets 1</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Magnets_1_sigma10.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-3-300x208.png" alt="&sigma;=10" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Magnets_1_sigma30.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-4-300x208.png" alt="&sigma;=30" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Magnets_1_sigma50.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-5-300x208.png" alt="&sigma;=50" width="100" height="70"></a></td>
</tr>
<tr>
<td>Vespa</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Vespa_sigma10.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-6-300x208.png" alt="&sigma;=10" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Vespa_sigma30.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-7-300x208.png" alt="&sigma;=30" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Vespa_sigma50.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_7_7-8-300x208.png" alt="&sigma;=50" width="100" height="70"></a></td>
</tr>
</tbody>
</table>

Below, we show results for lenslet camera (Lytro Illum) noise removal.

<table style="text-align: center; width: 100%;" border="0" cellspacing="2" cellpadding="2" align="center">
<tbody>
<tr>
<td>Color Chart 1</td>
<td>Desktop</td>
<td>ISO Chart 12</td>
<td>Magnets 1</td>
</tr>
<tr>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Color_Chart_1.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_07_07-300x208.png" alt="Color Chart 1" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Desktop.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_07_07-1-300x208.png" alt="Desktop" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_ISO_Chart_12.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_07_07-2-300x208.png" alt="ISO Chart 12" width="100" height="70"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/LFcomparisonSidebySide_Magnets_1.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2017/08/SAI_07_07-3-300x208.png" alt="Magnets 1" width="100" height="70"></a></td>
</tr>
</tbody>
</table>


<h3 id="avgres">Average PSNR results</h3>

The &#916;PSNR lines in Tables 1 and 2 correspond to the PSNR gap between the proposed approach and the best state-of-the-art method.
Values highlighted in bold correspond to the best performing method for a given noise level.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center">
  <caption> <b>Table 1 - </b> Average denoising performances in PSNR for the EPFL dataset (Lytro Illum).</caption>
  
  <tr><td></td>					<td>&#963;=10</td><td>&#963;=20</td><td>&#963;=30</td><td>&#963;=40</td><td>&#963;=50</td></tr>
  <tr><td>HF4D</td>				<td>31.070</td><td>25.798</td><td>22.607</td><td>20.338</td><td>18.586</td></tr>
  <tr><td>BM3D</td>				<td>35.421</td><td>32.852</td><td>31.357</td><td>30.247</td><td>29.321</td></tr>
  <tr><td>BM3D EPI</td>			<td>36.088</td><td>33.476</td><td>31.905</td><td>30.712</td><td>29.671</td></tr>
  <tr><td>VBM4D</td>			<td>36.075</td><td>33.522</td><td>31.923</td><td>30.674</td><td>29.630</td></tr>
  <tr><td>VBM4D EPI</td>		<td>36.129</td><td>33.510</td><td>31.925</td><td>30.719</td><td>29.721</td></tr>
  <tr><td>LFMB5D 1st step</td>	<td>34.388</td><td>32.810</td><td>31.684</td><td>30.743</td><td>29.911</td></tr>
  <tr><td>LFMB5D 2nd step</td>	<td><b>36.503</b></td><td><b>34.214</b></td><td><b>32.868</b></td><td><b>31.843</b></td><td><b>30.987</b></td></tr>
  <tr><td>&#916;PSNR</td>		<td>0.374</td><td>0.692</td><td>0.943</td><td>1.124</td><td>1.266</td></tr></tr>
</table>

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center">
  <caption> <b>Table 2 - </b> Average denoising performances in PSNR for the Stanford dataset (Gantry).</caption>

  <tr><td></td>					<td>&#963;=10</td><td>&#963;=20</td><td>&#963;=30</td><td>&#963;=40</td><td>&#963;=50</td></tr>
  <tr><td>HF4D</td>				<td>30.577</td><td>25.432</td><td>22.213</td><td>19.921</td><td>18.164</td></tr>
  <tr><td>BM3D</td>				<td>38.805</td><td>35.268</td><td>33.126</td><td>31.560</td><td>30.267</td></tr>
  <tr><td>BM3D EPI</td>			<td>38.895</td><td>35.645</td><td>33.489</td><td>31.896</td><td>30.594</td></tr>
  <tr><td>VBM4D</td>			<td>39.269</td><td>35.588</td><td>33.212</td><td>31.436</td><td>30.019</td></tr>
  <tr><td>VBM4D EPI</td>		<td>38.697</td><td>35.604</td><td>33.558</td><td>32.026</td><td>30.809</td></tr>
  <tr><td>LFMB5D 1st step</td>	<td>39.340</td><td>35.817</td><td>33.377</td><td>31.496</td><td>29.971</td></tr>
  <tr><td>LFMB5D 2nd step</td>	<td><b>40.389</b></td><td><b>37.772</b></td><td><b>36.031</b></td><td><b>34.6713</b></td><td><b>33.511</b></td></tr>
  <tr><td>&#916;PSNR</td>		<td>1.120</td><td>2.127</td><td>2.473</td><td>2.645</td><td>2.701</td></tr></tr>
</table>

<h3 id="detres">Detailed PSNR results</h3>

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center">
  <caption> <b>Table 3 - </b> Denoising performances in PSNR for each light field in the EPFL dataset (Lytro Illum).</caption>
  
  <tr><td></td>					<td>Ankylosorus & Dipplodocus 1</td><td>Bikes</td><td>Color Chart 1</td><td>Danger de Mort</td><td>Desktop</td><td>Flowers</td><td>Fountain & Vincent 2</td><td>Friends 1</td><td>ISO Chart 12</td><td>Magnets 1</td><td>Stone Pillar Outside</td><td>Vespa</td></tr>
  <tr><td colspan="13">HF4D</td></tr>
  <tr><td>&#963;=10</td>		<td>30.881</td><td>30.940</td><td>31.038</td><td>31.460</td><td>31.160</td><td>31.302</td><td>30.791</td><td>30.987</td><td>30.901</td><td>30.943</td><td>30.973</td><td>31.463</td></tr>
  <tr><td>&#963;=20</td>		<td>25.383</td><td>25.622</td><td>25.957</td><td>26.081</td><td>26.196</td><td>26.071</td><td>25.654</td><td>25.933</td><td>25.478</td><td>25.393</td><td>25.688</td><td>26.116</td></tr>
  <tr><td>&#963;=30</td>		<td>22.047</td><td>22.459</td><td>22.775</td><td>22.953</td><td>23.072</td><td>22.965</td><td>22.478</td><td>22.832</td><td>22.139</td><td>22.006</td><td>22.556</td><td>22.999</td></tr>
  <tr><td>&#963;=40</td>		<td>19.672</td><td>20.247</td><td>20.489</td><td>20.758</td><td>20.816</td><td>20.766</td><td>20.200</td><td>20.614</td><td>19.756</td><td>19.583</td><td>20.345</td><td>20.810</td></tr>
  <tr><td>&#963;=50</td>		<td>17.846</td><td>18.553</td><td>18.715</td><td>19.069</td><td>19.063</td><td>19.064</td><td>18.426</td><td>18.890</td><td>17.925</td><td>17.721</td><td>18.634</td><td>19.121</td></tr>
  
  <tr><td colspan="13">BM3D</td></tr>
  <tr><td>&#963;=10</td>		<td>36.094</td><td>34.760</td><td><b>35.711</b></td><td>35.039</td><td>35.706</td><td>34.250</td><td>34.308</td><td>35.518</td><td>34.948</td><td>36.044</td><td>33.928</td><td>38.750</td></tr>
  <tr><td>&#963;=20</td>		<td>34.604</td><td>31.834</td><td><b>33.640</b></td><td>32.082</td><td>33.034</td><td>30.996</td><td>31.373</td><td>32.804</td><td>32.537</td><td>34.485</td><td>30.870</td><td>36.310</td></tr>
  <tr><td>&#963;=30</td>		<td>33.661</td><td>30.175</td><td>32.426</td><td>30.368</td><td>31.528</td><td>29.182</td><td>29.734</td><td>31.231</td><td>31.027</td><td>33.405</td><td>29.319</td><td>34.226</td></tr>
  <tr><td>&#963;=40</td>		<td>32.865</td><td>28.968</td><td>31.456</td><td>29.136</td><td>30.432</td><td>27.910</td><td>28.559</td><td>30.083</td><td>29.876</td><td>32.452</td><td>28.310</td><td>32.919</td></tr>
  <tr><td>&#963;=50</td>		<td>32.140</td><td>27.939</td><td>30.606</td><td>28.140</td><td>29.531</td><td>26.893</td><td>27.574</td><td>29.135</td><td>28.912</td><td>31.564</td><td>27.565</td><td>31.849</td></tr>
  
  <tr><td colspan="13">BM3D EPI</td></tr>
  <tr><td>&#963;=10</td>		<td>36.131</td><td>35.589</td><td>34.977</td><td>36.097</td><td>37.061</td><td>35.831</td><td>34.637</td><td>36.763</td><td>35.065</td><td><b>36.286</b></td><td>35.284</td><td>39.332</td></tr>
  <tr><td>&#963;=20</td>		<td>34.754</td><td>32.635</td><td>32.726</td><td>33.077</td><td>33.894</td><td>32.534</td><td>31.818</td><td>34.141</td><td>32.440</td><td>34.881</td><td>32.280</td><td>36.532</td></tr>
  <tr><td>&#963;=30</td>		<td>33.853</td><td>30.979</td><td>31.256</td><td>31.275</td><td>31.903</td><td>30.607</td><td>30.199</td><td>32.494</td><td>30.966</td><td>33.921</td><td>30.765</td><td>34.638</td></tr>
  <tr><td>&#963;=40</td>		<td>32.951</td><td>29.783</td><td>30.126</td><td>29.839</td><td>30.781</td><td>29.188</td><td>29.032</td><td>31.192</td><td>29.963</td><td>32.937</td><td>29.658</td><td>33.094</td></tr>
  <tr><td>&#963;=50</td>		<td>32.032</td><td>28.779</td><td>29.102</td><td>28.542</td><td>29.866</td><td>27.992</td><td>28.126</td><td>30.079</td><td>29.219</td><td>31.936</td><td>28.637</td><td>31.746</td></tr>

  <tr><td colspan="13">VBM4D</td></tr>
  <tr><td>&#963;=10</td>		<td>35.966</td><td>35.628</td><td>35.401</td><td>36.008</td><td>36.464</td><td>35.967</td><td>34.742</td><td>36.631</td><td>35.326</td><td>36.101</td><td>35.467</td><td>39.195</td></tr>
  <tr><td>&#963;=20</td>		<td>34.219</td><td>32.772</td><td>33.302</td><td>33.049</td><td>33.869</td><td>32.776</td><td>32.104</td><td>33.914</td><td>33.040</td><td>34.421</td><td>32.483</td><td>36.310</td></tr>
  <tr><td>&#963;=30</td>		<td>33.036</td><td>31.065</td><td>32.014</td><td>31.266</td><td>32.242</td><td>30.840</td><td>30.557</td><td>32.241</td><td>31.549</td><td>33.190</td><td>30.714</td><td>34.358</td></tr>
  <tr><td>&#963;=40</td>		<td>32.013</td><td>29.792</td><td>30.947</td><td>29.941</td><td>30.965</td><td>29.406</td><td>29.391</td><td>30.965</td><td>30.350</td><td>32.103</td><td>29.388</td><td>32.831</td></tr>
  <tr><td>&#963;=50</td>		<td>31.074</td><td>28.762</td><td>29.999</td><td>28.868</td><td>29.891</td><td>28.282</td><td>28.430</td><td>29.900</td><td>29.316</td><td>31.117</td><td>28.327</td><td>31.592</td></tr>
  
  <tr><td colspan="13">VBM4D EPI</td></tr>
  <tr><td>&#963;=10</td>		<td><b>36.374</b></td><td>35.692</td><td>35.515</td><td>36.059</td><td>36.467</td><td>35.648</td><td>34.638</td><td>36.685</td><td>35.334</td><td>36.326</td><td>35.537</td><td>39.271</td></tr>
  <tr><td>&#963;=20</td>		<td>34.303</td><td>32.865</td><td>33.081</td><td>33.175</td><td>33.860</td><td>32.708</td><td>31.892</td><td>34.057</td><td>32.885</td><td>34.330</td><td>32.589</td><td>36.376</td></tr>
  <tr><td>&#963;=30</td>		<td>33.025</td><td>31.185</td><td>31.618</td><td>31.446</td><td>32.317</td><td>30.966</td><td>30.300</td><td>32.445</td><td>31.391</td><td>33.058</td><td>30.918</td><td>34.433</td></tr>
  <tr><td>&#963;=40</td>		<td>31.978</td><td>29.951</td><td>30.467</td><td>30.172</td><td>31.131</td><td>29.689</td><td>29.119</td><td>31.225</td><td>30.242</td><td>32.006</td><td>29.721</td><td>32.927</td></tr>
  <tr><td>&#963;=50</td>		<td>31.045</td><td>28.960</td><td>29.502</td><td>29.145</td><td>30.129</td><td>28.678</td><td>28.161</td><td>30.203</td><td>29.280</td><td>31.081</td><td>28.767</td><td>31.697</td></tr>  

  <tr><td colspan="13">LFMB5D 1st step</td></tr>
  <tr><td>&#963;=10</td>		<td>35.269</td><td>33.123</td><td>33.287</td><td>34.717</td><td>34.300</td><td>34.016</td><td>32.885</td><td>34.820</td><td>33.792</td><td>35.167</td><td>34.173</td><td>37.103</td></tr>
  <tr><td>&#963;=20</td>		<td>34.333</td><td>31.594</td><td>32.098</td><td>32.660</td><td>32.773</td><td>32.097</td><td>31.117</td><td>33.280</td><td>31.997</td><td>34.435</td><td>31.745</td><td>35.597</td></tr>
  <tr><td>&#963;=30</td>		<td>33.690</td><td>30.415</td><td>31.343</td><td>31.207</td><td>31.652</td><td>30.567</td><td>29.958</td><td>32.071</td><td>30.791</td><td>33.772</td><td>30.367</td><td>34.370</td></tr>
  <tr><td>&#963;=40</td>		<td>33.024</td><td>29.459</td><td>30.688</td><td>30.011</td><td>30.725</td><td>29.266</td><td>29.080</td><td>31.089</td><td>29.851</td><td>33.073</td><td>29.393</td><td>33.259</td></tr>
  <tr><td>&#963;=50</td>		<td>32.334</td><td>28.616</td><td>30.037</td><td>28.993</td><td>29.881</td><td>28.221</td><td>28.366</td><td>30.166</td><td>29.055</td><td>32.290</td><td>28.577</td><td>32.396</td></tr>  
  
  <tr><td colspan="13">LFMB5D 2nd step</td></tr>
  <tr><td>&#963;=10</td>		<td>   35.854    </td><td><b>36.275</b></td><td>   35.263    </td><td><b>36.868</b></td><td><b>36.767</b></td><td><b>36.813</b></td><td><b>34.941</b></td><td><b>37.406</b></td><td><b>35.661</b></td><td>   36.062    </td><td><b>36.213</b></td><td><b>39.910</b></td></tr>
  <tr><td>&#963;=20</td>		<td><b>34.791</b></td><td><b>33.577</b></td><td>   33.612    </td><td><b>33.954</b></td><td><b>34.538</b></td><td><b>33.690</b></td><td><b>32.334</b></td><td><b>34.958</b></td><td><b>33.423</b></td><td><b>35.200</b></td><td><b>32.942</b></td><td><b>37.549</b></td></tr>
  <tr><td>&#963;=30</td>		<td><b>34.216</b></td><td><b>32.002</b></td><td><b>32.736</b></td><td><b>32.295</b></td><td><b>33.192</b></td><td><b>31.779</b></td><td><b>30.873</b></td><td><b>33.482</b></td><td><b>31.975</b></td><td><b>34.565</b></td><td><b>31.272</b></td><td><b>36.030</b></td></tr>
  <tr><td>&#963;=40</td>		<td><b>33.667</b></td><td><b>30.851</b></td><td><b>32.028</b></td><td><b>31.037</b></td><td><b>32.156</b></td><td><b>30.352</b></td><td><b>29.872</b></td><td><b>32.382</b></td><td><b>30.910</b></td><td><b>33.938</b></td><td><b>30.143</b></td><td><b>34.773</b></td></tr>
  <tr><td>&#963;=50</td>		<td><b>33.086</b></td><td><b>29.908</b></td><td><b>31.390</b></td><td><b>30.027</b></td><td><b>31.292</b></td><td><b>29.245</b></td><td><b>29.106</b></td><td><b>31.463</b></td><td><b>30.040</b></td><td><b>33.267</b></td><td><b>29.246</b></td><td><b>33.769</b></td></tr>  
  
</table>

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center">
  <caption> <b>Table 4 - </b> Denoising performances in PSNR for each light field in the Stanford dataset (Gantry).</caption>
  																						

  <tr><td></td>					<td>Amethyst</td><td>Bracelet</td><td>Chess</td><td>Eucalyptus Flowers</td><td>Jelly beans</td><td>Lego Bulldozer</td><td>Lego Knights</td><td>Lego Truck</td><td>Tarot Cards and Crystal Ball (Large Angle)</td><td>Tarot Cards and Crystal Ball (Small Angle)</td><td>The Stanford Bunny</td><td>Treasure Chest</td></tr>
  <tr><td colspan="13">HF4D</td></tr>
  <tr><td>&#963;=10</td>		<td>31.374</td><td>30.464</td><td>31.362</td><td>29.466</td><td>31.330</td><td>29.850</td><td>30.352</td><td>31.315</td><td>29.080</td><td>31.050</td><td>31.361</td><td>29.913</td></tr>
  <tr><td>&#963;=20</td>		<td>25.862</td><td>25.201</td><td>25.816</td><td>25.175</td><td>25.468</td><td>25.243</td><td>25.210</td><td>26.000</td><td>24.738</td><td>25.430</td><td>25.578</td><td>25.463</td></tr>
  <tr><td>&#963;=30</td>		<td>22.543</td><td>21.864</td><td>22.576</td><td>22.154</td><td>22.035</td><td>22.181</td><td>21.966</td><td>22.813</td><td>21.660</td><td>22.088</td><td>22.189</td><td>22.492</td></tr>
  <tr><td>&#963;=40</td>		<td>20.200</td><td>19.508</td><td>20.284</td><td>19.908</td><td>19.671</td><td>19.967</td><td>19.646</td><td>20.570</td><td>19.396</td><td>19.756</td><td>19.818</td><td>20.325</td></tr>
  <tr><td>&#963;=50</td>		<td>18.406</td><td>17.735</td><td>18.525</td><td>18.143</td><td>17.901</td><td>18.259</td><td>17.867</td><td>18.845</td><td>17.650</td><td>17.989</td><td>18.017</td><td>18.633</td></tr>
  
  <tr><td colspan="13">BM3D</td></tr>
  <tr><td>&#963;=10</td>		<td>37.549</td><td>38.438</td><td>40.829</td><td>35.177</td><td>44.865</td><td>37.429</td><td>40.135</td><td>38.394</td><td>38.154</td><td>37.914</td><td>39.814</td><td>36.962</td></tr>
  <tr><td>&#963;=20</td>		<td>33.964</td><td>34.565</td><td>37.542</td><td>31.246</td><td>41.867</td><td>33.814</td><td>36.666</td><td>34.917</td><td>34.578</td><td>34.267</td><td>36.744</td><td>33.047</td></tr>
  <tr><td>&#963;=30</td>		<td>31.925</td><td>32.290</td><td>35.398</td><td>29.093</td><td>39.696</td><td>31.680</td><td>34.489</td><td>32.796</td><td>32.445</td><td>32.099</td><td>34.788</td><td>30.816</td></tr>
  <tr><td>&#963;=40</td>		<td>30.518</td><td>30.645</td><td>33.777</td><td>27.600</td><td>37.985</td><td>30.156</td><td>32.872</td><td>31.259</td><td>30.884</td><td>30.511</td><td>33.320</td><td>29.195</td></tr>
  <tr><td>&#963;=50</td>		<td>29.422</td><td>29.271</td><td>32.412</td><td>26.354</td><td>36.548</td><td>28.934</td><td>31.566</td><td>30.037</td><td>29.586</td><td>29.175</td><td>32.137</td><td>27.764</td></tr>
  
  <tr><td colspan="13">BM3D EPI</td></tr>
  <tr><td>&#963;=10</td>		<td>38.915</td><td>38.879</td><td>41.029</td><td>35.688</td><td>43.871</td><td>37.076</td><td>38.430</td><td>39.171</td><td>36.684</td><td>37.955</td><td>41.338</td><td>37.703</td></tr>
  <tr><td>&#963;=20</td>		<td>36.234</td><td>35.472</td><td>38.871</td><td>31.760</td><td>41.685</td><td>33.122</td><td>34.473</td><td>36.180</td><td>32.283</td><td>34.970</td><td>39.329</td><td>33.358</td></tr>
  <tr><td>&#963;=30</td>		<td>34.481</td><td>32.174</td><td>37.207</td><td>29.398</td><td>40.229</td><td>30.714</td><td>32.317</td><td>33.970</td><td>29.493</td><td>33.040</td><td><b>37.754</b></td><td>31.090</td></tr>
  <tr><td>&#963;=40</td>		<td>31.200</td><td>31.430</td><td>35.894</td><td>27.748</td><td>39.080</td><td>29.031</td><td>31.015</td><td>32.307</td><td>27.596</td><td>31.557</td><td><b>36.484</b></td><td>29.412</td></tr>
  <tr><td>&#963;=50</td>		<td>29.875</td><td>28.992</td><td>34.800</td><td>26.529</td><td>38.127</td><td>27.814</td><td>30.117</td><td>31.003</td><td>26.232</td><td>30.331</td><td><b>35.305</b></td><td>27.997</td></tr>

  <tr><td colspan="13">VBM4D</td></tr>
  <tr><td>&#963;=10</td>		<td>38.561</td><td>38.997</td><td>41.004</td><td>36.531</td><td>43.941</td><td>38.334</td><td>40.253</td><td>39.164</td><td>37.906</td><td>38.433</td><td>40.225</td><td>37.882</td></tr>
  <tr><td>&#963;=20</td>		<td>34.974</td><td>35.156</td><td>37.391</td><td>32.917</td><td>40.098</td><td>34.558</td><td>36.525</td><td>35.580</td><td>34.190</td><td>34.830</td><td>36.736</td><td>34.094</td></tr>
  <tr><td>&#963;=30</td>		<td>32.657</td><td>32.748</td><td>34.921</td><td>30.679</td><td>37.411</td><td>32.142</td><td>34.066</td><td>33.211</td><td>31.893</td><td>32.551</td><td>34.476</td><td>31.792</td></tr>
  <tr><td>&#963;=40</td>		<td>30.944</td><td>30.959</td><td>33.041</td><td>29.020</td><td>35.341</td><td>30.370</td><td>32.212</td><td>31.440</td><td>30.192</td><td>30.853</td><td>32.763</td><td>30.099</td></tr>
  <tr><td>&#963;=50</td>		<td>29.592</td><td>29.526</td><td>31.535</td><td>27.704</td><td>33.667</td><td>28.980</td><td>30.729</td><td>30.035</td><td>28.834</td><td>29.494</td><td>31.384</td><td>28.755</td></tr>
  
  <tr><td colspan="13">VBM4D EPI</td></tr>
  <tr><td>&#963;=10</td>		<td>38.417</td><td>38.139</td><td>41.133</td><td>34.468</td><td>44.278</td><td>36.959</td><td>39.320</td><td>38.809</td><td>36.960</td><td>37.853</td><td>40.927</td><td>37.097</td></tr>
  <tr><td>&#963;=20</td>		<td>35.772</td><td>34.897</td><td>38.521</td><td>31.829</td><td>41.131</td><td>33.521</td><td>36.227</td><td>35.460</td><td>33.350</td><td>35.077</td><td>38.127</td><td>33.340</td></tr>
  <tr><td>&#963;=30</td>		<td>34.016</td><td>32.810</td><td>36.608</td><td>29.999</td><td>38.950</td><td>31.355</td><td>34.077</td><td>33.236</td><td>31.105</td><td>33.233</td><td>36.245</td><td>31.061</td></tr>
  <tr><td>&#963;=40</td>		<td>32.708</td><td>31.263</td><td>35.095</td><td>28.634</td><td>37.267</td><td>29.785</td><td>32.443</td><td>31.556</td><td>29.496</td><td>31.851</td><td>34.832</td><td>29.384</td></tr>
  <tr><td>&#963;=50</td>		<td>31.668</td><td>30.033</td><td>33.864</td><td>27.561</td><td>35.901</td><td>28.556</td><td>31.175</td><td>30.202</td><td>28.241</td><td>30.749</td><td>33.706</td><td>28.054</td></tr>  
  
  <tr><td colspan="13">LFMB5D 1st step</td></tr>
  <tr><td>&#963;=10</td>		<td>38.847</td><td>38.907</td><td>40.797</td><td>36.710</td><td>43.926</td><td>38.630</td><td>40.351</td><td>39.385</td><td>37.043</td><td>38.432</td><td>40.826</td><td>38.229</td></tr>
  <tr><td>&#963;=20</td>		<td>35.529</td><td>35.037</td><td>37.415</td><td>33.399</td><td>40.399</td><td>35.026</td><td>36.972</td><td>35.873</td><td>33.355</td><td>35.228</td><td>36.787</td><td>34.786</td></tr>
  <tr><td>&#963;=30</td>		<td>33.190</td><td>32.515</td><td>35.162</td><td>31.306</td><td>37.294</td><td>32.624</td><td>34.781</td><td>33.479</td><td>30.940</td><td>32.856</td><td>33.911</td><td>32.469</td></tr>
  <tr><td>&#963;=40</td>		<td>31.368</td><td>30.857</td><td>33.466</td><td>29.658</td><td>34.400</td><td>30.828</td><td>33.038</td><td>31.664</td><td>29.122</td><td>30.773</td><td>32.078</td><td>30.702</td></tr>
  <tr><td>&#963;=50</td>		<td>29.862</td><td>29.587</td><td>32.046</td><td>28.174</td><td>32.257</td><td>29.321</td><td>31.588</td><td>30.176</td><td>27.749</td><td>29.021</td><td>30.743</td><td>29.129</td></tr>  
  
  <tr><td colspan="13">LFMB5D 2nd step</td></tr>
  <tr><td>&#963;=10</td>		<td><b>39.593</b></td><td><b>39.884</b></td><td><b>42.158</b></td><td><b>37.263</b></td><td><b>45.636</b></td><td><b>39.603</b></td><td><b>41.598</b></td><td><b>40.357</b></td><td><b>38.354</b></td><td><b>39.344</b></td><td><b>41.881</b></td><td><b>39.003</b></td></tr>
  <tr><td>&#963;=20</td>		<td><b>37.020</b></td><td><b>36.988</b></td><td><b>40.045</b></td><td><b>34.332</b></td><td><b>43.826</b></td><td><b>36.762</b></td><td><b>38.936</b></td><td><b>37.852</b></td><td><b>35.371</b></td><td><b>36.673</b></td><td><b>39.383</b></td><td><b>36.071</b></td></tr>
  <tr><td>&#963;=30</td>		<td><b>35.257</b></td><td><b>35.305</b></td><td><b>38.437</b></td><td><b>32.575</b></td><td><b>42.281</b></td><td><b>34.878</b></td><td><b>37.167</b></td><td><b>36.062</b></td><td><b>33.618</b></td><td><b>35.007</b></td><td>   37.560    </td><td><b>34.227</b></td></tr>
  <tr><td>&#963;=40</td>		<td><b>33.874</b></td><td><b>34.077</b></td><td><b>37.056</b></td><td><b>31.286</b></td><td><b>41.016</b></td><td><b>33.438</b></td><td><b>35.761</b></td><td><b>34.592</b></td><td><b>32.301</b></td><td><b>33.708</b></td><td>   36.090    </td><td><b>32.858</b></td></tr>
  <tr><td>&#963;=50</td>		<td><b>32.685</b></td><td><b>33.020</b></td><td><b>35.851</b></td><td><b>30.142</b></td><td><b>39.920</b></td><td><b>32.155</b></td><td><b>34.598</b></td><td><b>33.343</b></td><td><b>31.269</b></td><td><b>32.615</b></td><td>   34.837    </td><td><b>31.693</b></td></tr>  
  
</table>


<!-- <h3 id="visres">Visual results</h3>

We show here side by side comparisons of noisy and de-noised light fields.
On the top left corner of each video is highlighted the sub-aperture image being displayed. Note that some videos may exhibit encoding artifacts.

First, we show results for different synthetic noise levels where &#963; corresponds to the white gaussian noise standard deviation (click on a &#963; to start a video).

<ul>
  <li>Lego Knights: <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_LegoKnights_sigma10.mp4">&#963;=10</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_LegoKnights_sigma30.mp4">&#963;=30</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_LegoKnights_sigma50.mp4">&#963;=50</a>
  </li>
  <li>Amethyst: <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Amethyst_sigma10.mp4">&#963;=10</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Amethyst_sigma30.mp4">&#963;=30</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Amethyst_sigma50.mp4">&#963;=50</a>
  </li>
  <li>Tarot Cards and Crystal Ball (Small Angle): <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_TarotCardsandCrystalBall_SmallAngle_sigma10.mp4">&#963;=10</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_TarotCardsandCrystalBall_SmallAngle_sigma30.mp4">&#963;=30</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_TarotCardsandCrystalBall_SmallAngle_sigma50.mp4">&#963;=50</a>
  </li>
  <li>Bikes: <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Bikes_sigma10.mp4">&#963;=10</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Bikes_sigma30.mp4">&#963;=30</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Bikes_sigma50.mp4">&#963;=50</a>
  </li>
  <li>Magnets 1: <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Magnets_1_sigma10.mp4">&#963;=10</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Magnets_1_sigma30.mp4">&#963;=30</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Magnets_1_sigma50.mp4">&#963;=50</a>
  </li>
  <li>Vespa: <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Vespa_sigma10.mp4">&#963;=10</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Vespa_sigma30.mp4">&#963;=30</a> / <a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Vespa_sigma50.mp4">&#963;=50</a>
  </li>
</ul>


Below, we show results for lenslet camera (Lytro) noise removal.

<ul>
  <li><a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Color_Chart_1.mp4">Color Chart 1</a></li>
  <li><a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Desktop.mp4">Desktop</a></li>
  <li><a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_ISO_Chart_12.mp4">ISO Chart 12</a></li>
  <li><a href="https://www.scss.tcd.ie/~alainm/vid/LFBM5D/LFcomparisonSidebySide_Magnets_1.mp4">Magnets  1</a></li>
</ul> -->