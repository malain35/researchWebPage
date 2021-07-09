+++
abstract = "Light  field  imaging  enables  us  to  capture  all  lightrays   in   a   visual   scene.   As   light   fields   are   four-dimensional,their  captures  come  with  an  increased  amount  of  informationto  take  advantage  of.  This  has  stimulated  ongoing  light  fieldspecific  research  into  virtual  viewpoints  and  shallow  depth  offield  rendering,  commonly  called  refocusing.  However,  the  com-putation time and memory required to perform these operationscan  make  tasks  such  as  real-time  rendering  impractical.  Onesolution  is  to  exploit  the  salient  information  of  light  fields  tofocus  resources  on  regions  that  attract  visual  attention  whenusing  these  algorithms.  Although  saliency  estimation  methodsfor light fields have been previously explored, these focus mainlyon  salient  object  segmentation  with  the  goal  of  generating  onesaliency  map  per  light  field.Aiming  to  create  a  basis  for  a  4D  saliency  prediction  modelanalogous to light fields, this paper proposes a saliency estimationmethod   specific   to   light   fields   that   considers   the   refocusingoperation.   The   proposed   method   modifies   an   existing   viewrendering algorithm with focus guidance, obtained from the lightfield disparity. This facilitates the construction of saliency mapswithout  the  need  to  render  the  corresponding  view  itself,  whichwill help to speed up processing operations that are compatible.The results show that the proposed saliency estimation approachyields  very  good  predictions  of  visual  attention  across  multipleplanes of the light field. We anticipate that this approach can beextended  for  a  range  of  rendering  applications."
abstract_short = ""
authors = ["A. Gill†", "E. Zerman", "M. Alain", "M. Le Pendu", "A. Smolic"]
date = "2021-06-14"
highlight = true
image_preview = ""
math = true
publication = "International Conference on Quality of Multimedia Experience"
publication_short = "QoMEX 2021"
publication_types = ["1"]
selected = false
title = "Focus Guided Light Field Saliency Estimation"
url_code = ""
url_dataset = ""
url_pdf = "pdf/preprint21_qomex_focusGuidedLFSal.pdf"
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
url = "https://v-sense.scss.tcd.ie/research/light-fields/light-field-saliency-estimation/"

[header]
image = "headers/lfSaliency.png"
caption = ""

+++

<h3>Additional Results</h3>
<p>Due to the page limit of the venue to which we submitted our work, we could not provide all the results in the manuscript.&nbsp;Here we will share additional results for our study.</p>
<p>The data we used were from 4 different databases: <a href="http://lightfield.stanford.edu/">Stanford</a><sup>1</sup>, <a href="https://mmspg.epfl.ch/EPFL-light-field-image-dataset">EPFL</a><sup>2</sup>, <a href="https://lightfield-analysis.uni-konstanz.de/">HCI Heidelberg<sup>3</sup></a>.</p>
<table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="1" align="center">
<tbody>
<tr>
<td>
<p style="text-align: left;">
</p></td>
<td style="text-align: left;">&nbsp;</td>
<td><img class="alignnone size-full wp-image-6866" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/07/label.png" alt="" width="6000" height="365"></td>
</tr>
<tr>
<td>
<p>Boardgames<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="size-full wp-image-6808 alignnone" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/boardgames_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Boardgames<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6809" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/boardgames_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Dino<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6810" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/dino_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Dino<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6811" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/dino_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Dishes<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6812" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/dishes_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Dishes<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6813" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/dishes_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Friends<sup>2</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6814" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/Friends_obj1QomexGrid.png" alt="" width="6125" height="694"></td>
</tr>
<tr>
<td>
<p>Friends<sup>2</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6815" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/Friends_obj2QomexGrid.png" alt="" width="6125" height="694"></td>
</tr>
<tr>
<td>
<p>LegoKnights<sup>1</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6816" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/LegoKnights_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>LegoKnights<sup>1</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6817" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/LegoKnights_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Medieval<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6818" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/medieval2_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Medieval<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6819" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/medieval2_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Pens<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6820" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/pens_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Pens<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6821" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/pens_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Platonic<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6822" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/platonic_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Platonic<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6823" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/platonic_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Sideboard<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6824" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/sideboard_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Sideboard<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6825" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/sideboard_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Table<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6826" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/table_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Table<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6827" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/table_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Tarot-Large<sup>1</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6828" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/TarotCardsandCrystalBall_LargeAngle_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Tarot-Large<sup>1</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6829" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/TarotCardsandCrystalBall_LargeAngle_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Tarot-Small<sup>1</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6830" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/TarotCardsandCrystalBall_SmallAngle_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Tarot-Small<sup>1</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6831" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/TarotCardsandCrystalBall_SmallAngle_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Tower<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6832" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/tower_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Tower<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6833" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/tower_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Town<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6834" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/town_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Town<sup>3</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6835" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/town_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td>
<p>Treasure<sup>1</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6836" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/TreasureChest_obj1QomexGrid.png" alt="" width="6125" height="833"></td>
</tr>
<tr>
<td>
<p>Treasure<sup>1</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6837" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/TreasureChest_obj2QomexGrid.png" alt="" width="6125" height="833"></td>
</tr>
<tr>
<td>
<p>Vespa<sup>2</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6838" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/Vespa_obj1QomexGrid.png" alt="" width="6125" height="694"></td>
</tr>
<tr>
<td>
<p>Vespa<sup>2</sup></p>
</td>
<td>
<p>Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6839" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/Vespa_obj2QomexGrid.png" alt="" width="6125" height="694"></td>
</tr>
<tr>
<td>
<p>Vinyl<sup>3</sup></p>
</td>
<td>
<p>Region1</p>
</td>
<td><img class="alignnone size-full wp-image-6840" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/vinyl_obj1QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
<tr>
<td style="text-align: left;">
<p>Vinyl<sup>3</sup></p>
</td>
<td>
<p style="text-align: left;">Region2</p>
</td>
<td><img class="alignnone size-full wp-image-6841" src="https://v-sense.scss.tcd.ie/wp-content/uploads/2021/04/vinyl_obj2QomexGrid.png" alt="" width="6125" height="999"></td>
</tr>
</tbody>
</table>
<p><strong>&nbsp;</strong></p>
