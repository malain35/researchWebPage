+++
abstract = "Style transfer involves combining the style of one image with the content of another to form a new image. Unlike traditional two-dimensional images which only capture the spatial intensity of light rays, four-dimensional light fields also capture the angular direction of the light rays. Thus, applying style transfer to a light field requires to not only render convincing style transfer for each view, but also to preserve its angular structure. We present a novel optimization-based method for light field style transfer which iteratively propagates the style transfer from the centre view towards the outer views while enforcing local angular consistency. For this purpose, a new initialisation method and angular loss function is proposed for the optimization process. In addition, since style transfer for light field is an emerging topic, no clear evaluation procedure is available. Thus, we investigate the use of a recently proposed metric designed to evaluate light field angular consistency, as well as a proposed variant."
abstract_short = ""
authors = ["D. Egan", "M. Alain", "A. Smolic"]
date = "2021-06-06"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Conference on Acoustics, Speech and Signal Processing"
publication_short = "ICASSP 2021"
publication_types = ["1"]
selected = true
title = "Light Field Style Transfer With Local Angular Consistency"
url_code = ""
url_dataset = ""
url_pdf = "pdf/Neural_Style_Transfer_for_Light_Field.pdf"
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
url = "https://v-sense.scss.tcd.ie/research/a-spatio-angular-binary-descriptor-for-fast-light-field-inter-view-matching/"

[header]
image = "headers/vsense_webpage_featured_image-1140x570.png"
caption = ""

+++


<!-- wp:heading -->
<h2>Implementation</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The code will soon be available.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Presentation</h2>
<!-- /wp:heading -->

<iframe width="560" height="315" src="https://www.youtube.com/embed/ujjgKTouk0o" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



<!-- wp:heading -->
<h2>Additional results</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h3>Light field individual viewpoints</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We show in videos below (click on an image to start a video) all the views for the original and stylized light fields. Videos were created by firs scanning the views using a horizontal snake pattern going from the top left to the bottom right view, followed by a vertical snake pattern going from the bottom right to the top left view. Note that the video baseline results were obtained using the horizontal snake pattern going from the top left to the bottom right view, thus while the first half of the videos may appear consistent, the second half of the videos reveal that the angular consistency is not fully preserved.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="0" align="center">
<tbody>
<tr>
<td></td>
<td>Original</td>
<td>Image baseline [1]</td>
<td>Video baseline [2]</td>
<td>Hart et al. [3]</td>
<td>Ours</td>
</tr>
<tr>
<td>Swans [4]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Org_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Org_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Gatys_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Gatys_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Video_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Video_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Hart_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Hart_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Ours_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Ours_viewpoints_snake_scan.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Bikes [5]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Org_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Org_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Gatys_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Gatys_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Video_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Video_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Hart_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Hart_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Ours_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Ours_viewpoints_snake_scan.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Table [6]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Org_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Org_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Gatys_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Gatys_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Video_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Video_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Hart_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Hart_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Ours_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Ours_viewpoints_snake_scan.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Herbs [6]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Org_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Org_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Gatys_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Gatys_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Video_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Video_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td>n/a</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Ours_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Ours_viewpoints_snake_scan.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Lego Knights [7]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Org_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Org_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Gatys_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Gatys_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Video_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Video_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Hart_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Hart_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Ours_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Ours_viewpoints_snake_scan.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Crystal Ball [7]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Org_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Org_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Gatys_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Gatys_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Video_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Video_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Hart_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Hart_viewpoints_snake_scan.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Ours_viewpoints_snake_scan.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Ours_viewpoints_snake_scan.png" width="100" height="100"></a></td>
</tr>
</tbody>
</table></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h3>Focal stacks</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We show in videos below (click on an image to start a video) focal stacks generated from the original and stylized light fields. Refocused images were generated using the shift-and-sum algorithm with a full aperture. Videos are showing the focal stacks from back to front and front to back.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><table style="text-align: center; width: 100%;" cellspacing="2" cellpadding="2" border="0" align="center">
<tbody>
<tr>
<td></td>
<td>Original</td>
<td>Image baseline [1]</td>
<td>Video baseline [2]</td>
<td>Hart et al. [3]</td>
<td>Ours</td>
</tr>
<tr>
<td>Swans [4]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Org_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Org_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Gatys_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Gatys_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Video_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Video_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Hart_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Hart_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Ours_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/swans_Ours_focalstack.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Bikes [5]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Org_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Org_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Gatys_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Gatys_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Video_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Video_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Hart_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Hart_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Ours_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/bikes_Ours_focalstack.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Table [6]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Org_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Org_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Gatys_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Gatys_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Video_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Video_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Hart_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Hart_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Ours_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/table_Ours_focalstack.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Herbs [6]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Org_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Org_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Gatys_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Gatys_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Video_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Video_focalstack.png" width="100" height="100"></a></td>
<td>n/a</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Ours_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/herbs_Ours_focalstack.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Lego Knights [7]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Org_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Org_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Gatys_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Gatys_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Video_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Video_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Hart_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Hart_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Ours_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/lego_Ours_focalstack.png" width="100" height="100"></a></td>
</tr>
<tr>
<td>Crystal Ball [7]</td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Org_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Org_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Gatys_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Gatys_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Video_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Video_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Hart_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Hart_focalstack.png" width="100" height="100"></a></td>
<td><a href="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Ours_focalstack.mp4"><img src="https://v-sense.scss.tcd.ie/wp-content/uploads/2020/10/crystalball_Ours_focalstack.png" width="100" height="100"></a></td>
</tr>
</tr>
</tbody>
</table></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>References</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><p>[1] Gatys, Leon A., Alexander S. Ecker, and Matthias Bethge. "Image style transfer using convolutional neural networks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2016.</p>
<p>[2] Ruder, Manuel, Alexey Dosovitskiy, and Thomas Brox. "Artistic style transfer for videos." German Conference on Pattern Recognition. Springer, Cham, 2016.</p>
<p>[3] Hart, David, Bryan Morse, and Jessica Greenland. "Style Transfer for Light Field Photography." The IEEE Winter Conference on Applications of Computer Vision. 2020.</p>
<p>[4] Rerabek, Martin, and Touradj Ebrahimi. "New light field image dataset." 8th International Conference on Quality of Multimedia Experience (QoMEX). 2016.</p>
<p>[5] Abhilash Sunder Raj, Michael Lowney, Raj Shah, and Gordon  Wetzstein, "Stanford Lytro light field archive", <a href="http://lightfields.stanford.edu/LF2016.html">http://lightfields.stanford.edu/LF2016.html</a></p>
<p>[6] Honauer, Katrin, et al. "A dataset and evaluation methodology for depth estimation on 4d light fields." Asian Conference on Computer Vision. Springer, Cham, 2016.</p>
<p>[7] "The Stanford light field archive", <a href="http://lightfield.stanford.edu/lfs.html">http://lightfield.stanford.edu/lfs.html</a>  </p>
</p>
<!-- /wp:paragraph -->
