+++
abstract = "In this paper, we propose a novel scheme for scalable image coding based on the concept of epitome. An epitome can be seen as a factorized representation of an image. Focusing on spatial scalability, the enhancement layer of the proposed scheme contains only the epitome of the input image. The pixels of the enhancement layer not contained in the epitome are then restored using two approaches inspired from local learning-based super-resolution methods. In the first method, a locally linear embedding model is learned on base layer patches and then applied to the corresponding epitome patches to reconstruct the enhancement layer. The second approach learns linear mappings between pairs of co-located base layer and epitome patches. Experiments have shown that the significant improvement of the rate-distortion performances can be achieved compared with the Scalable extension of HEVC (SHVC)."
abstract_short = ""
authors = ["M. Alain", "C. Guillemot", "D. Thoreau", "P. Guillotel"]
date = "2017-05-09"
highlight = true
image_preview = "headers/epitome_EL.png"
math = true
publication = "IEEE Transaction on Image Processing"
publication_short = "IEEE TIP 2017"
publication_types = ["2"]
selected = true
title = "Scalable image coding based on epitomes"
url_code = ""
url_dataset = ""
url_pdf = "pdf/Epitome_scalable.pdf"
url_project = ""
url_slides = ""
url_video = ""

#[[url_custom]]
#name = "BibTex"
#url = "bib/AlainTIP2017.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "http://ieeexplore.ieee.org/document/7922592/"

[[url_custom]]
name = "INRIA"
url = "https://www.irisa.fr/temics/demos/epitomeScalableCoding/epitomeScalableCoding.html"

[header]
image = ""
caption = ""

+++

## Context and Goal

The concept of epitome was first introduced by Jojic et al. as the condensed representation (meaning its size is only a fraction of the original size) of an image containing the essence of its the textural properties. This original epitomic model is based on a patch-based probabilistic approach, and has different applications in segmentation, denoising, recognition, indexing or texture synthesis.  
Several epitomic models have been since proposed, such as the factorized representation of Wang et al. dedicated to texture mapping, or its extension designed for image coding purposes by Chérigui et al. The epitome is in this case the union of epitome charts which are pieces of repeatable textures found in the image. The search for self-similar or repeatable texture patterns, based on the KLT or a block matching (BM) algorithm, is known to be memory and time consuming.  
In this work, we propose a clustering-based technique to reduce the self-similarities search complexity.

## Approach

The main steps of the proposed scheme for scalable image coding are depicted in Fig. 1.  

In the proposed scheme, the enhancement layer (EL) consists in an epitome of the input image. Consequently, at the decoder side, the EL patches not contained in the epitome are missing, but the corresponding base layer (BL) patches are known. We thus propose to restore the full enhancement layer by taking advantage of the known representative texture patches available in the EL epitome charts. (More explanations on the epitome generation are available [here]() or in the papers listed [at the end of this page.](#references))  

The epitomes are encoded with a scalable scheme as an enhancement layer. The blocks not belonging to the epitome are directly copied from the decoded base layer, thus their rate-cost is practically non-existent.  

The non-epitome part of the enhancement layer is restored using methods derived from local learning-based super-resolution methods, and can be summarized in the three following steps: K-NN search, learning step, and processing step. These steps are shown in Fig. 2. A first method is proposed relying on Locally Linear Embedding, noted E-LLE. A second technique called E-LLM, based on Local Linear Mapping, is also studied.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/eptmSc_files/schema.png" caption="Proposed scheme for scalable image coding." >}}

{{< figure src="https://www.scss.tcd.ie/~alainm/img/eptmSc_files/schema_restoration.png" caption="Main steps of the epitome-based restoration." >}}

## Experimental Results

The experiments are performed on the test images listed in Table I, obtained from the HEVC test sequences. The base layer images are obtained by down sampling the input image with a factor 2x2, using the SHVC down-sampling filter available with the SHM software (ver. 9.0). The BL images are encoded with HEVC, using the HM software (ver. 15.0). We then use the SHM software (ver. 9.0) to encode the corresponding enhancement layers. Both layers are encoded with the following quantization steps: QP = 22, 27, 32, 37.  

For each input image, 3 to 4 epitomes of different sizes are genererated, ranging from 30% to 90% of the input image sizes.

<table style="text-align: center; width: 60%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 1 - Test images</caption>

<tbody>

<tr>

<th>Class</th>

<th>Image</th>

<th>Size</th>

</tr>

<tr>

<td>B</td>

<td>BasketballDrive</td>

<td>1920x1080</td>

</tr>

<tr>

<td>B</td>

<td>Cactus</td>

<td>1920x1080</td>

</tr>

<tr>

<td>B</td>

<td>Ducks</td>

<td>1920x1080</td>

</tr>

<tr>

<td>B</td>

<td>Kimono</td>

<td>1920x1080</td>

</tr>

<tr>

<td>B</td>

<td>ParkScene</td>

<td>1920x1080</td>

</tr>

<tr>

<td>B</td>

<td>Tennis</td>

<td>1920x1080</td>

</tr>

<tr>

<td>B</td>

<td>Terrace</td>

<td>1920x1080</td>

</tr>

<tr>

<td>C</td>

<td>BasketballDrill</td>

<td>832x480</td>

</tr>

<tr>

<td>C</td>

<td>Keiba</td>

<td>832x480</td>

</tr>

<tr>

<td>C</td>

<td>Mall</td>

<td>832x480</td>

</tr>

<tr>

<td>C</td>

<td>PartyScene</td>

<td>832x480</td>

</tr>

<tr>

<td>D</td>

<td>BasketballPass</td>

<td>416x240</td>

</tr>

<tr>

<td>D</td>

<td>BlowingBubbles</td>

<td>416x240</td>

</tr>

<tr>

<td>D</td>

<td>RaceHorses</td>

<td>416x240</td>

</tr>

<tr>

<td>D</td>

<td>Square</td>

<td>416x240</td>

</tr>

<tr>

<td>E</td>

<td>City</td>

<td>1280x720</td>

</tr>

</tbody>

</table>

We show in Fig. 3 the Bjontegaard rate gains averaged over all sequences depending on the epitome size. The complete results are given in Table 2. We show in Fig. 4 the RD curve of the City image, which behavior is representative of the set of test images. We first show (left) the RD curve for both E-LLE and E-LLM methods with the biggest epitome size (best RD performances). We then show (right) the RD curve for the E-LLE with different epitome sizes.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/eptmSc_files/RD_perf_size_eptm.png" caption="Average RD performances of the different restoration methods against SHVC depending on the epitome size." >}}

{{< figure src="https://www.scss.tcd.ie/~alainm/img/eptmSc_files/City_RD_curve_method_and_eptm_size.png" caption="Left: E-LLE and E-LLM methods, epitome size = 91.59% of input image. Right: E-LLE method, with different epitome sizes." >}}

We show in Fig. 5 the running time of the different methods for each image class (_i.e._ size) depending on the epitome size. On the left, we show the running time of the epitome generation at the encoder side. On the right, we show the running time of the restoration step at the decoder side. Note that the epitome generation algorithm was implemented in C++ while the restoration methods were implemented in Matlab.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/eptmSc_files/running_time_eptm_post_proc.png" caption="Left: Epitome generation running time depending on the epitome size for different image classes. Right: Post-processing running time of the different restoration methods depending on the epitome size for different image classes." >}}

In the table below are listed the exhaustive Bjontegaard rate gains obtained with the proposed methods against SHVC.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 2 -  Bjontegaard rate gains SHVC depending on the epitome size.</caption>

<tbody>

<tr>

<td rowspan="2">Image</td>

<td rowspan="2">Epitome size (% of input image)</td>

<td colspan="2">BD rate gains (%)</td>

</tr>

<tr>

<td>E-LLE</td>

<td>E-LLM</td>

</tr>

<tr>

<td rowspan="4">BasketballDrive</td>

<td>90.62</td>

<td>-20.07</td>

<td>-19.61</td>

</tr>

<tr>

<td>64.10</td>

<td>-15.94</td>

<td>-13.70</td>

</tr>

<tr>

<td>49.33</td>

<td>-13.66</td>

<td>-8.89</td>

</tr>

<tr>

<td>32.34</td>

<td>-9.70</td>

<td>-0.08</td>

</tr>

<tr>

<td rowspan="4">Cactus</td>

<td>79.85</td>

<td>-18.19</td>

<td>-16.46</td>

</tr>

<tr>

<td>71.24</td>

<td>-17.67</td>

<td>-15.14</td>

</tr>

<tr>

<td>60.66</td>

<td>-16.33</td>

<td>-13.01</td>

</tr>

<tr>

<td>48.33</td>

<td>-11.63</td>

<td>-7.42</td>

</tr>

<tr>

<td rowspan="3">Ducks</td>

<td>89.63</td>

<td>-19.52</td>

<td>-19.07</td>

</tr>

<tr>

<td>77.41</td>

<td>-16.71</td>

<td>-14.21</td>

</tr>

<tr>

<td>48.28</td>

<td>2.88</td>

<td>10.28</td>

</tr>

<tr>

<td rowspan="4">Kimono</td>

<td>90.13</td>

<td>-21.75</td>

<td>-21.42</td>

</tr>

<tr>

<td>75.53</td>

<td>-15.98</td>

<td>-12.63</td>

</tr>

<tr>

<td>59.36</td>

<td>-17.37</td>

<td>-15.08</td>

</tr>

<tr>

<td>35.34</td>

<td>-15.82</td>

<td>-12.31</td>

</tr>

<tr>

<td rowspan="4">ParkScene</td>

<td>86.58</td>

<td>-16.88</td>

<td>-16.45</td>

</tr>

<tr>

<td>73.55</td>

<td>-15.10</td>

<td>-13.84</td>

</tr>

<tr>

<td>61.99</td>

<td>-10.69</td>

<td>-7.50</td>

</tr>

<tr>

<td>47.18</td>

<td>-3.94</td>

<td>2.89</td>

</tr>

<tr>

<td rowspan="4">Tennis</td>

<td>64.49</td>

<td>-23.04</td>

<td>-21.91</td>

</tr>

<tr>

<td>50.44</td>

<td>-22.03</td>

<td>-19.61</td>

</tr>

<tr>

<td>43.12</td>

<td>-19.90</td>

<td>-16.59</td>

</tr>

<tr>

<td>32.22</td>

<td>-18.42</td>

<td>-13.13</td>

</tr>

<tr>

<td rowspan="4">Terrace</td>

<td>78.46</td>

<td>-13.27</td>

<td>-12.49</td>

</tr>

<tr>

<td>66.39</td>

<td>-11.32</td>

<td>-9.57</td>

</tr>

<tr>

<td>53.31</td>

<td>-6.81</td>

<td>-3.01</td>

</tr>

<tr>

<td>43.50</td>

<td>-0.50</td>

<td>9.03</td>

</tr>

<tr>

<td rowspan="4">City</td>

<td>91.59</td>

<td>-10.05</td>

<td>-8.76</td>

</tr>

<tr>

<td>82.44</td>

<td>-6.24</td>

<td>-1.59</td>

</tr>

<tr>

<td>66.81</td>

<td>3.27</td>

<td>17.75</td>

</tr>

<tr>

<td>39.52</td>

<td>28.00</td>

<td>59.96</td>

</tr>

<tr>

<td rowspan="4">BasketballDrill</td>

<td>87.05</td>

<td>-6.52</td>

<td>-5.50</td>

</tr>

<tr>

<td>59.94</td>

<td>-2.82</td>

<td>1.08</td>

</tr>

<tr>

<td>42.63</td>

<td>-1.62</td>

<td>4.44</td>

</tr>

<tr>

<td>28.53</td>

<td>3.18</td>

<td>13.08</td>

</tr>

<tr>

<td rowspan="4">Keiba</td>

<td>93.59</td>

<td>-6.71</td>

<td>-6.42</td>

</tr>

<tr>

<td>81.28</td>

<td>-3.69</td>

<td>-1.99</td>

</tr>

<tr>

<td>63.53</td>

<td>3.24</td>

<td>7.75</td>

</tr>

<tr>

<td>40.77</td>

<td>16.06</td>

<td>23.52</td>

</tr>

<tr>

<td rowspan="4">Mall</td>

<td>92.95</td>

<td>-18.20</td>

<td>-16.76</td>

</tr>

<tr>

<td>76.28</td>

<td>-0.50</td>

<td>-2.13</td>

</tr>

<tr>

<td>66.15</td>

<td>-4.13</td>

<td>3.04</td>

</tr>

<tr>

<td>50.26</td>

<td>6.75</td>

<td>27.54</td>

</tr>

<tr>

<td rowspan="4">PartyScene</td>

<td>94.82</td>

<td>-5.44</td>

<td>-4.29</td>

</tr>

<tr>

<td>81.12</td>

<td>-1.18</td>

<td>7.20</td>

</tr>

<tr>

<td>67.56</td>

<td>8.83</td>

<td>25.96</td>

</tr>

<tr>

<td>49.13</td>

<td>26.89</td>

<td>57.15</td>

</tr>

<tr>

<td rowspan="4">BasketballPass</td>

<td>77.76</td>

<td>-16.17</td>

<td>-13.15</td>

</tr>

<tr>

<td>66.60</td>

<td>-14.07</td>

<td>-7.25</td>

</tr>

<tr>

<td>56.41</td>

<td>-0.53</td>

<td>10.48</td>

</tr>

<tr>

<td>42.31</td>

<td>5.72</td>

<td>28.21</td>

</tr>

<tr>

<td rowspan="4">BlowingBubbles</td>

<td>87.56</td>

<td>-6.33</td>

<td>-3.29</td>

</tr>

<tr>

<td>73.33</td>

<td>-2.73</td>

<td>3.65</td>

</tr>

<tr>

<td>58.85</td>

<td>3.27</td>

<td>13.95</td>

</tr>

<tr>

<td>36.92</td>

<td>16.81</td>

<td>44.03</td>

</tr>

<tr>

<td rowspan="4">RaceHorses</td>

<td>91.03</td>

<td>-16.08</td>

<td>-15.67</td>

</tr>

<tr>

<td>79.23</td>

<td>-4.49</td>

<td>-3.03</td>

</tr>

<tr>

<td>58.14</td>

<td>6.69</td>

<td>20.64</td>

</tr>

<tr>

<td>36.67</td>

<td>23.45</td>

<td>63.23</td>

</tr>

<tr>

<td rowspan="4">Square</td>

<td>80.77</td>

<td>-6.45</td>

<td>-2.97</td>

</tr>

<tr>

<td>71.41</td>

<td>-5.88</td>

<td>1.08</td>

</tr>

<tr>

<td>61.09</td>

<td>-2.00</td>

<td>4.75</td>

</tr>

<tr>

<td>48.72</td>

<td>9.80</td>

<td>31.68</td>

</tr>

</tbody>

</table>

## References

*   Nebojsa Jojic, Brendan J. Frey, Anitha Kannan, **Epitomic analysis of appearance and shape**, _ICCV 2003._ [[PDF]](http://research.microsoft.com/en-us/um/people/jojic/epitome/JojicFreyKannan_iccv03.pdf) [[Web]](http://research.microsoft.com/en-us/um/people/jojic/epitome.htm)
*   Huamin Wang, Yonatan Wexler, Eyal Ofek, Hugues Hoppe, **Factoring repeated content within and among images**, _SIGGRAPH 2008._ [[PDF]](http://research.microsoft.com/en-us/um/people/hoppe/factorimage.pdf) [[Web]](http://research.microsoft.com/en-us/um/people/hoppe/proj/factorimage)
*   Safa Cherigui, [Christine Guillemot](http://www.irisa.fr/temics/staff/guillemot/), [Dominique Thoreau](http://www.technicolor.com/en/dominique-thoreau), [Philippe Guilltotel](http://www.technicolor.com/en/philippe-guillotel) and [Patrick Perez](http://www.technicolor.com/en/patrick-perez), **Epitome-based image compression using translational sub-pel mapping**, _MMSP 2011._ [[PDF]](https://hal.inria.fr/hal-00994418/document)
