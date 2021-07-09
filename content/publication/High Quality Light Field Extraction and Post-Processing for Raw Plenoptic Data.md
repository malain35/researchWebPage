+++
abstract = "Light field technology has reached a certain level ofmaturity in recent years, and its applications in both computervision research and industry are offering new perspectives forcinematography and virtual reality. Several methods of captureexist, each with its own advantages and drawbacks. One of thesemethods involves the use of handheld plenoptic cameras. Whilethese cameras offer freedom and ease of use, they also sufferfrom various visual artefacts and inconsistencies. We proposein this paper an advanced pipeline that enhances their output.After extracting sub-aperture images from the RAW imageswith our demultiplexing method, we perform three correctionsteps. We first remove hot pixel artefacts, then correct colourinconsistencies between views using a colour transfer method, andfinally we apply a state of the art light field denoising techniqueto ensure a high image quality. An in-depth analysis is providedfor every step of the pipeline, as well as their interaction withinthe system. We compare our approach to existing state of theart sub-aperture image extracting algorithms, using a number ofmetrics as well as a subjective experiment. Finally, we showcasethe positive impact of our system on a number of relevant lightfield applications."
abstract_short = ""
authors = ["P. Matysiak", "M. Grogan", "M. Le Pendu", "M. Alain", "E. Zerman", "A. Smolic"]
date = "2020-01-23"
highlight = true
image_preview = ""
math = true
publication = "IEEE Transactions on Image Processing"
publication_short = "IEEE TIP 2020"
publication_types = ["2"]
selected = false
title = "High Quality Light Field Extraction and Post-Processing for Raw Plenoptic Data"
url_code = ""
url_dataset = ""
url_pdf = "pdf/TIP_HQLF_authorV_small.pdf"
url_project = ""
url_slides = ""
url_video = ""

#[[url_custom]]
#name = "BibTex"
#url = "bib/MatysiakICIP2018.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "https://ieeexplore.ieee.org/document/8967224"

[[url_custom]]
name = "V-SENSE"
url = "https://v-sense.scss.tcd.ie/?p=1548"

[header]
image = "headers/enhancement_pipeline.png"
caption = ""

+++

<h2>Implementation</h2>
All of our code is available here (please cite the appropriate papers if you use or adapt these codes in your work):

- <a href="https://github.com/V-Sense/LFToolbox-CLIM_VSENSE">RAW data decoding</a>
- <a href="https://github.com/V-Sense/LFToolbox_Recolouring_HPR">Recolouring</a>
- <a href="https://github.com/V-Sense/LFBM5D">Denoising</a>

<h2>Datasets</h2>
Many of the Light Field datasets we processed are available for direct use in clean form here. Please cite our paper "A Pipeline for Lenslet Light Field Quality Enhancement", ICIP 2018, if you use any of these data in you work. Two versions are available, without or with our denoising step:

- <a href="http://v-sense.scss.tcd.ie/Datasets/LFPipeline_datasets.tar.gz">Dataset (without denoising)</a>
- <a href="http://v-sense.scss.tcd.ie/Datasets/LFPipeline_datasets_denoised.tar.gz">Dataset (with denoising)</a>

<h2>Additional results</h2>
Our pipeline was applied on a subset of the freely available <a href="https://mmspg.epfl.ch/EPFL-light-field-image-dataset">EPFL</a><sup>1</sup> and <a href="https://www.irisa.fr/temics/demos/lightField/CLIM/DataSoftware.html">INRIA</a><sup>2</sup> datasets.
<h3>Successful colour correction</h3>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<tbody>
<tr>
<td></td>
<td style="text-align: center; vertical-align: middle;">Centre view (palette)</td>
<td style="text-align: center; vertical-align: middle;">Original external view</td>
<td style="text-align: center; vertical-align: middle;">'Centre' recolouring</td>
<td style="text-align: center; vertical-align: middle;">'Prop' recolouring</td>
<td style="text-align: center; vertical-align: middle;">'Prop+centre' reco</td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Ankylosaurus_and_ Diplodocus_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1577" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_ori_0707-300x208.png" alt="" width="300" height="208"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1576" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_ori_0010-300x208.png" alt="" width="300" height="208"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1575" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_c_0010-300x208.png" alt="" width="300" height="208"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1579" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_p_0010-300x208.png" alt="" width="300" height="208"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1578" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/anky_pc_0010-300x208.png" alt="" width="300" height="208"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Bee_1<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1582" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1581" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1580" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1584" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1583" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Bee_2<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1706" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1705" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1704" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1708" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1707" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1711" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1710" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1709" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1713" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1712" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">ChezEdgar<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1587" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1586" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1585" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1589" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1588" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/chezed_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Friends_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1592" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1591" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1590" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1594" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1593" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/friends_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Fruits<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1597" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1596" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1595" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1599" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1598" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fruits_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Magnets_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1602" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1601" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1600" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1604" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1603" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/magnets_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Posts<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1607" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1606" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1605" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1609" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1608" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Rose<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1612" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1611" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1610" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1614" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1613" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/rose_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Vespa<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_ori_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1617" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_ori_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_ori_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1616" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_ori_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_c_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1615" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_c_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_p_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1619" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_p_0010-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_pc_0010.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1618" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/vespa_pc_0010-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
</tbody>
</table>
<h3>Video examples</h3>
<h4>Left side : our decoding; right side : our recolouring (Bee_2<sup>2</sup>).</h4>
<div class="vsense-center">

[video width="1250" height="434" mp4="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bee2.mp4" loop="true"][/video]

</div>
<h4>Left side : our recolouring; right side : our denoising (Bee_2<sup>2</sup>).</h4>
<div class="vsense-center">

[video width="1250" height="434" mp4="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_Bee2_sigma5.mp4" loop="true"][/video]

</div>
<h4>Left side : our decoding; right side : our recolouring (Color_Chart_1<sup>1</sup>).</h4>
<div class="vsense-center">

[video width="1250" height="434" mp4="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_ColorChart.mp4" loop="true"][/video]

</div>
<h4>Left side : our recolouring; right side : our denoising (Color_Chart_1<sup>1</sup>).</h4>
<div class="vsense-center">

[video width="1250" height="434" mp4="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/LFcomparisonSideBySide_ColorChart_sigma5.mp4" loop="true"][/video]

</div>
<h3>Epipolar images</h3>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Horizontal epipolar images.</b></caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Dansereau decoding</td>
<td style="text-align: center;">Our pipeline ('centre')</td>
<td style="text-align: center;">Our pipeline ('prop')</td>
<td style="text-align: center;">Our pipeline ('p+c')</td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Bee_1<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_4-deno_dans_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1624" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_4-deno_dans_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_1-deno_c_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1621" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_1-deno_c_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_2-deno_p_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1622" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_2-deno_p_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_3-deno_pc_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1623" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_3-deno_pc_row-300x100.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Bee_2<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_4-deno_dans_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1628" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_4-deno_dans_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_1-deno_c_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1625" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_1-deno_c_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_2-deno_p_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1626" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_2-deno_p_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_3-deno_pc_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1627" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_3-deno_pc_row-300x100.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_4-deno_dans_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1632" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_4-deno_dans_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_1-deno_c_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1629" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_1-deno_c_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_2-deno_p_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1630" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_2-deno_p_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_3-deno_pc_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1631" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_3-deno_pc_row-300x100.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Fruits<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_4-deno_dans_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1636" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_4-deno_dans_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_1-deno_c_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1633" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_1-deno_c_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_2-deno_p_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1634" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_2-deno_p_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_3-deno_pc_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1635" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_3-deno_pc_row-300x100.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Magnets_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_4-deno_dans_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1640" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_4-deno_dans_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_1-deno_c_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1637" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_1-deno_c_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_2-deno_p_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1638" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_2-deno_p_row-300x100.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_3-deno_pc_row.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1639" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_3-deno_pc_row-300x100.png" alt="" width="150" height="150"></a></td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Vertical epipolar images.</b></caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center; vertical-align: middle;">Dansereau decoding</td>
<td style="text-align: center; vertical-align: middle;">Our pipeline ('centre')</td>
<td style="text-align: center; vertical-align: middle;">Our pipeline ('prop')</td>
<td style="text-align: center; vertical-align: middle;">Our pipeline ('p+c')</td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Bee_1<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_4-deno_dans_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1648" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_4-deno_dans_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_1-deno_c_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1645" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_1-deno_c_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_2-deno_p_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1646" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_2-deno_p_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_3-deno_pc_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1647" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee1_3-deno_pc_col-144x300.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Bee_2<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_4-deno_dans_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1652" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_4-deno_dans_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_1-deno_c_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1649" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_1-deno_c_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_2-deno_p_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1650" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_2-deno_p_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_3-deno_pc_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1651" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/bee2_3-deno_pc_col-144x300.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_4-deno_dans_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1656" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_4-deno_dans_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_1-deno_c_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1653" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_1-deno_c_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_2-deno_p_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1654" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_2-deno_p_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_3-deno_pc_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1655" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/cchart_3-deno_pc_col-144x300.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Fruits<sup>2</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_4-deno_dans_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1668" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_4-deno_dans_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_1-deno_c_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1665" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_1-deno_c_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_2-deno_p_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1666" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_2-deno_p_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_3-deno_pc_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1667" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fru_3-deno_pc_col-144x300.png" alt="" width="150" height="150"></a></td>
</tr>
<tr>
<td style="text-align: left; vertical-align: middle;">Magnets_1<sup>1</sup></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_4-deno_dans_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1672" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_4-deno_dans_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_1-deno_c_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1669" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_1-deno_c_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_2-deno_p_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1670" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_2-deno_p_col-144x300.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_3-deno_pc_col.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1671" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/mag_3-deno_pc_col-144x300.png" alt="" width="150" height="150"></a></td>
</tr>
</tbody>
</table>
<h3>Fail cases</h3>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption>'Centre' recolouring scheme fail cases. First picture is the centre view (palette), the rest are fail cases (different views in the light field). (Color_Chart_1<sup>1</sup> dataset)</caption>
<tbody>
<tr>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/goal_0707.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1683" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/goal_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1304.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1682" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1304-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1200.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1681" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1200-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1102.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1679" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1102-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1100.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1678" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1100-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1012.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1677" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_reco_1012-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption>Examples of tiny details not being registered properly during colour correction. First picture is the centre view (palette), second is a fail case (neighbouring view of the centre one). (Posts<sup>2</sup> dataset)</caption>
<tbody>
<tr>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_goal_0707.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1812" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_goal_0707-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_fail_tiny_0708.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-1811" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/posts_fail_tiny_0708-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption>Recolouring fail cases when extreme specular effects are present. First picture is the centre view (palette), the rest are fail cases (different views in the light field). (Vespa<sup>1</sup> dataset)</caption>
<tbody>
<tr>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/goal_0707-2.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1688" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/goal_0707-2-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_spec_1112.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1687" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_spec_1112-300x208.png" alt="" width="150" height="150"></a></td>
<td style="text-align: center; vertical-align: middle;"><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_spec_1012.png" target="_blank" rel="noopener"><img class="alignnone size-thumbnail wp-image-1686" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2018/02/fail_spec_1012-300x208.png" alt="" width="150" height="150"></a></td>
</tr>
</tbody>
</table>
<!-- <sup>1</sup> M. Rerabek and T. Ebrahimi, “New Light Field ImageDataset”, inProc. QoMEX, 2016.
<sup>2</sup> “Inria Lytro Illum dataset”, http://www.irisa.fr/temics/demos/lightField/CLIM/DataSoftware.html. -->
<h2>Detailed metric results</h2>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Table 1 - </b> Average recolouring results using PSNR. Higher values are better.</caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Decoded</td>
<td style="text-align: center;">Prop</td>
<td style="text-align: center;">Centre</td>
<td style="text-align: center;">Prop+centre</td>
</tr>
<tr>
<td style="text-align: left;">Ankylosaurus_and_Diplodocus_1<sup>1</sup></td>
<td style="text-align: center;">29.2905</td>
<td style="text-align: center;">30.4249</td>
<td style="text-align: center;">30.1865</td>
<td style="text-align: center;">30.3422</td>
</tr>
<tr>
<td style="text-align: left;">Bee_1<sup>2</sup></td>
<td style="text-align: center;">22.5770</td>
<td style="text-align: center;">24.0342</td>
<td style="text-align: center;">23.8479</td>
<td style="text-align: center;">23.9856</td>
</tr>
<tr>
<td style="text-align: left;">Bee_2<sup>2</sup></td>
<td style="text-align: center;">20.7177</td>
<td style="text-align: center;">21.7383</td>
<td style="text-align: center;">21.5678</td>
<td style="text-align: center;">21.6599</td>
</tr>
<tr>
<td style="text-align: left;">ChezEdgar<sup>2</sup></td>
<td style="text-align: center;">25.8484</td>
<td style="text-align: center;">26.7639</td>
<td style="text-align: center;">26.7429</td>
<td style="text-align: center;">26.7728</td>
</tr>
<tr>
<td style="text-align: left;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center;">21.0754</td>
<td style="text-align: center;">21.9253</td>
<td style="text-align: center;">21.6420</td>
<td style="text-align: center;">21.9139</td>
</tr>
<tr>
<td style="text-align: left;">Friends_1<sup>1</sup></td>
<td style="text-align: center;">26.9947</td>
<td style="text-align: center;">27.3831</td>
<td style="text-align: center;">27.2762</td>
<td style="text-align: center;">27.3273</td>
</tr>
<tr>
<td style="text-align: left;">Fruits<sup>2</sup></td>
<td style="text-align: center;">21.0893</td>
<td style="text-align: center;">21.5367</td>
<td style="text-align: center;">21.4133</td>
<td style="text-align: center;">21.4574</td>
</tr>
<tr>
<td style="text-align: left;">Magnets_1<sup>1</sup></td>
<td style="text-align: center;">27.8008</td>
<td style="text-align: center;">28.4443</td>
<td style="text-align: center;">28.3576</td>
<td style="text-align: center;">28.4102</td>
</tr>
<tr>
<td style="text-align: left;">Posts<sup>2</sup></td>
<td style="text-align: center;">25.4259</td>
<td style="text-align: center;">29.3566</td>
<td style="text-align: center;">28.8164</td>
<td style="text-align: center;">29.2133</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Table 2 - </b> Average recolouring results using SSIM. Higher values are better.</caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Decoded</td>
<td style="text-align: center;">Prop</td>
<td style="text-align: center;">Centre</td>
<td style="text-align: center;">Prop+centre</td>
</tr>
<tr>
<td style="text-align: left;">Ankylosaurus_and_Diplodocus_1<sup>1</sup></td>
<td style="text-align: center;">0.9049</td>
<td style="text-align: center;">0.9324</td>
<td style="text-align: center;">0.9300</td>
<td style="text-align: center;">0.9317</td>
</tr>
<tr>
<td style="text-align: left;">Bee_1<sup>2</sup></td>
<td style="text-align: center;">0.6550</td>
<td style="text-align: center;">0.7212</td>
<td style="text-align: center;">0.7099</td>
<td style="text-align: center;">0.7191</td>
</tr>
<tr>
<td style="text-align: left;">Bee_2<sup>2</sup></td>
<td style="text-align: center;">0.5790</td>
<td style="text-align: center;">0.6156</td>
<td style="text-align: center;">0.6101</td>
<td style="text-align: center;">0.6135</td>
</tr>
<tr>
<td style="text-align: left;">ChezEdgar<sup>2</sup></td>
<td style="text-align: center;">0.9058</td>
<td style="text-align: center;">0.9152</td>
<td style="text-align: center;">0.9166</td>
<td style="text-align: center;">0.9162</td>
</tr>
<tr>
<td style="text-align: left;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center;">0.8023</td>
<td style="text-align: center;">0.8165</td>
<td style="text-align: center;">0.8057</td>
<td style="text-align: center;">0.8170</td>
</tr>
<tr>
<td style="text-align: left;">Friends_1<sup>1</sup></td>
<td style="text-align: center;">0.9239</td>
<td style="text-align: center;">0.9299</td>
<td style="text-align: center;">0.9290</td>
<td style="text-align: center;">0.9297</td>
</tr>
<tr>
<td style="text-align: left;">Fruits<sup>2</sup></td>
<td style="text-align: center;">0.6317</td>
<td style="text-align: center;">0.6379</td>
<td style="text-align: center;">0.6369</td>
<td style="text-align: center;">0.6375</td>
</tr>
<tr>
<td style="text-align: left;">Magnets_1<sup>1</sup></td>
<td style="text-align: center;">0.9106</td>
<td style="text-align: center;">0.9346</td>
<td style="text-align: center;">0.9330</td>
<td style="text-align: center;">0.9348</td>
</tr>
<tr>
<td style="text-align: left;">Posts<sup>2</sup></td>
<td style="text-align: center;">0.8054</td>
<td style="text-align: center;">0.8659</td>
<td style="text-align: center;">0.8560</td>
<td style="text-align: center;">0.8637</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Table 3 - </b> Average recolouring results using S-CIELab. Lower values are better.</caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Decoded</td>
<td style="text-align: center;">Prop</td>
<td style="text-align: center;">Centre</td>
<td style="text-align: center;">Prop+centre</td>
</tr>
<tr>
<td style="text-align: left;">Ankylosaurus_and_Diplodocus_1<sup>1</sup></td>
<td style="text-align: center;">11.6821</td>
<td style="text-align: center;">7.2841</td>
<td style="text-align: center;">7.3169</td>
<td style="text-align: center;">7.2584</td>
</tr>
<tr>
<td style="text-align: left;">Bee_1<sup>2</sup></td>
<td style="text-align: center;">47.9358</td>
<td style="text-align: center;">33.7399</td>
<td style="text-align: center;">34.8856</td>
<td style="text-align: center;">33.8488</td>
</tr>
<tr>
<td style="text-align: left;">Bee_2<sup>2</sup></td>
<td style="text-align: center;">62.2390</td>
<td style="text-align: center;">58.6591</td>
<td style="text-align: center;">57.2721</td>
<td style="text-align: center;">57.9372</td>
</tr>
<tr>
<td style="text-align: left;">ChezEdgar<sup>2</sup></td>
<td style="text-align: center;">29.2363</td>
<td style="text-align: center;">21.7885</td>
<td style="text-align: center;">21.0047</td>
<td style="text-align: center;">21.2967</td>
</tr>
<tr>
<td style="text-align: left;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center;">36.2238</td>
<td style="text-align: center;">24.2762</td>
<td style="text-align: center;">26.1732</td>
<td style="text-align: center;">24.0729</td>
</tr>
<tr>
<td style="text-align: left;">Friends_1<sup>1</sup></td>
<td style="text-align: center;">13.5950</td>
<td style="text-align: center;">11.5322</td>
<td style="text-align: center;">11.0613</td>
<td style="text-align: center;">11.2397</td>
</tr>
<tr>
<td style="text-align: left;">Fruits<sup>2</sup></td>
<td style="text-align: center;">47.8697</td>
<td style="text-align: center;">46.9557</td>
<td style="text-align: center;">44.3578</td>
<td style="text-align: center;">45.0527</td>
</tr>
<tr>
<td style="text-align: left;">Magnets_1<sup>1</sup></td>
<td style="text-align: center;">15.0985</td>
<td style="text-align: center;">11.0375</td>
<td style="text-align: center;">10.7007</td>
<td style="text-align: center;">10.7644</td>
</tr>
<tr>
<td style="text-align: left;">Posts<sup>2</sup></td>
<td style="text-align: center;">23.6692</td>
<td style="text-align: center;">9.1165</td>
<td style="text-align: center;">9.9985</td>
<td style="text-align: center;">9.2863</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Table 4 - </b> Average recolouring results using CID. Lower values are better.</caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Decoded</td>
<td style="text-align: center;">Prop</td>
<td style="text-align: center;">Centre</td>
<td style="text-align: center;">Prop+centre</td>
</tr>
<tr>
<td style="text-align: left;">Ankylosaurus_and_Diplodocus_1<sup>1</sup></td>
<td style="text-align: center;">0.4394</td>
<td style="text-align: center;">0.2110</td>
<td style="text-align: center;">0.1993</td>
<td style="text-align: center;">0.2071</td>
</tr>
<tr>
<td style="text-align: left;">Bee_1<sup>2</sup></td>
<td style="text-align: center;">0.4277</td>
<td style="text-align: center;">0.2245</td>
<td style="text-align: center;">0.2210</td>
<td style="text-align: center;">0.2223</td>
</tr>
<tr>
<td style="text-align: left;">Bee_2<sup>2</sup></td>
<td style="text-align: center;">0.5007</td>
<td style="text-align: center;">0.4455</td>
<td style="text-align: center;">0.4433</td>
<td style="text-align: center;">0.4413</td>
</tr>
<tr>
<td style="text-align: left;">ChezEdgar<sup>2</sup></td>
<td style="text-align: center;">0.2260</td>
<td style="text-align: center;">0.2253</td>
<td style="text-align: center;">0.2201</td>
<td style="text-align: center;">0.2210</td>
</tr>
<tr>
<td style="text-align: left;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center;">0.4059</td>
<td style="text-align: center;">0.3869</td>
<td style="text-align: center;">0.3966</td>
<td style="text-align: center;">0.3876</td>
</tr>
<tr>
<td style="text-align: left;">Friends_1<sup>1</sup></td>
<td style="text-align: center;">0.1266</td>
<td style="text-align: center;">0.1141</td>
<td style="text-align: center;">0.1128</td>
<td style="text-align: center;">0.1130</td>
</tr>
<tr>
<td style="text-align: left;">Fruits<sup>2</sup></td>
<td style="text-align: center;">0.3110</td>
<td style="text-align: center;">0.3049</td>
<td style="text-align: center;">0.3004</td>
<td style="text-align: center;">0.3007</td>
</tr>
<tr>
<td style="text-align: left;">Magnets_1<sup>1</sup></td>
<td style="text-align: center;">0.5034</td>
<td style="text-align: center;">0.3056</td>
<td style="text-align: center;">0.3113</td>
<td style="text-align: center;">0.3112</td>
</tr>
<tr>
<td style="text-align: left;">Posts<sup>2</sup></td>
<td style="text-align: center;">0.0222</td>
<td style="text-align: center;">0.0216</td>
<td style="text-align: center;">0.0244</td>
<td style="text-align: center;">0.0228</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Table 5 - </b> Average recolouring results using Histogram distance. Lower values are better.</caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Decoded</td>
<td style="text-align: center;">Prop</td>
<td style="text-align: center;">Centre</td>
<td style="text-align: center;">Prop+centre</td>
</tr>
<tr>
<td style="text-align: left;">Ankylosaurus_and_Diplodocus_1<sup>1</sup></td>
<td style="text-align: center;">0.3068</td>
<td style="text-align: center;">0.1583</td>
<td style="text-align: center;">0.1591</td>
<td style="text-align: center;">0.1597</td>
</tr>
<tr>
<td style="text-align: left;">Bee_1<sup>2</sup></td>
<td style="text-align: center;">0.3419</td>
<td style="text-align: center;">0.2037</td>
<td style="text-align: center;">0.2153</td>
<td style="text-align: center;">0.2045</td>
</tr>
<tr>
<td style="text-align: left;">Bee_2<sup>2</sup></td>
<td style="text-align: center;">0.2354</td>
<td style="text-align: center;">0.2238</td>
<td style="text-align: center;">0.1841</td>
<td style="text-align: center;">0.2039</td>
</tr>
<tr>
<td style="text-align: left;">ChezEdgar<sup>2</sup></td>
<td style="text-align: center;">0.2189</td>
<td style="text-align: center;">0.1225</td>
<td style="text-align: center;">0.1234</td>
<td style="text-align: center;">0.1234</td>
</tr>
<tr>
<td style="text-align: left;">Color_Chart_1<sup>1</sup></td>
<td style="text-align: center;">0.2274</td>
<td style="text-align: center;">0.1540</td>
<td style="text-align: center;">0.1588</td>
<td style="text-align: center;">0.1536</td>
</tr>
<tr>
<td style="text-align: left;">Friends_1<sup>1</sup></td>
<td style="text-align: center;">0.1928</td>
<td style="text-align: center;">0.1185</td>
<td style="text-align: center;">0.1170</td>
<td style="text-align: center;">0.1179</td>
</tr>
<tr>
<td style="text-align: left;">Fruits<sup>2</sup></td>
<td style="text-align: center;">0.1930</td>
<td style="text-align: center;">0.1669</td>
<td style="text-align: center;">0.1375</td>
<td style="text-align: center;">0.1482</td>
</tr>
<tr>
<td style="text-align: left;">Magnets_1<sup>1</sup></td>
<td style="text-align: center;">0.2768</td>
<td style="text-align: center;">0.1545</td>
<td style="text-align: center;">0.1424</td>
<td style="text-align: center;">0.1497</td>
</tr>
<tr>
<td style="text-align: left;">Posts<sup>2</sup></td>
<td style="text-align: center;">0.4981</td>
<td style="text-align: center;">0.2388</td>
<td style="text-align: center;">0.2384</td>
<td style="text-align: center;">0.2437</td>
</tr>
</tbody>
</table>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<caption><b>Table 6 - </b> Average noise level before and after denoising. Lower values are better.</caption>
<tbody>
<tr>
<td></td>
<td style="text-align: center;">Decoded</td>
<td style="text-align: center;">Prop</td>
<td style="text-align: center;">Prop+denoising</td>
<td style="text-align: center;">Centre</td>
<td style="text-align: center;">Centre+denoising</td>
<td style="text-align: center;">Prop+centre+denoising</td>
</tr>
<tr>
<td style="text-align: left;">Ankylosaurus_and_Diplodocus_1<sup>1</sup></td>
<td>1.268</td>
<td>0.830</td>
<td>0.010</td>
<td>0.847</td>
<td>0.013</td>
<td>0.816</td>
<td>0.009</td>
</tr>
<tr>
<td style="text-align: left;">Bee_1<sup>2</sup></td>
<td>3.019</td>
<td>2.132</td>
<td>0.262</td>
<td>2.362</td>
<td>0.345</td>
<td>2.160</td>
<td>0.262</td>
</tr>
<tr>
<td style="text-align: left;">Bee_2<sup>2</sup></td>
<td>1.994</td>
<td>1.704</td>
<td>0.197</td>
<td>1.971</td>
<td>0.214</td>
<td>1.775</td>
<td>0.196</td>
</tr>
<tr>
<td style="text-align: left;">ChezEdgar<sup>2</sup></td>
<td>1.532</td>
<td>1.365</td>
<td>0.252</td>
<td>1.415</td>
<td>0.259</td>
<td>1.372</td>
<td>0.253</td>
</tr>
<tr>
<td style="text-align: left;">Color_Chart_1<sup>1</sup></td>
<td>1.294</td>
<td>1.239</td>
<td>0.090</td>
<td>1.386</td>
<td>0.130</td>
<td>1.248</td>
<td>0.090</td>
</tr>
<tr>
<td style="text-align: left;">Friends_1<sup>1</sup></td>
<td>0.584</td>
<td>0.563</td>
<td>0.110</td>
<td>0.570</td>
<td>0.105</td>
<td>0.586</td>
<td>0.113</td>
</tr>
<tr>
<td style="text-align: left;">Fruits<sup>2</sup></td>
<td>1.293</td>
<td>1.220</td>
<td>0.159</td>
<td>1.383</td>
<td>0.168</td>
<td>1.321</td>
<td>0.164</td>
</tr>
<tr>
<td style="text-align: left;">Magnets_1<sup>1</sup></td>
<td>1.196</td>
<td>0.812</td>
<td>0.008</td>
<td>0.890</td>
<td>0.021</td>
<td>0.825</td>
<td>0.011</td>
</tr>
<tr>
<td style="text-align: left;">Posts<sup>2</sup></td>
<td>1.622</td>
<td>0.956</td>
<td>0.008</td>
<td>1.092</td>
<td>0.022</td>
<td>0.956</td>
<td>0.008</td>
</tr>
</tbody>
</table>
<h2>References</h2>
[1] M. Rerabek and T. Ebrahimi, “New Light Field Image Dataset”, in Proc. QoMEX, 2016.
[2] “Inria lytro illum dataset”, http://www.irisa.fr/temics/demos/lightField/CLIM/DataSoftware.html.
