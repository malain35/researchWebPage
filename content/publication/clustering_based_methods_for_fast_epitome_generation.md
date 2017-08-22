+++
abstract = "This paper deals with epitome generation, mainly dedicated here to image coding applications. Existing approaches are known to be memory and time consuming due to exhaustive self-similarities search within the image for each non-overlapping block. We propose here a novel approach for epitome construction that first groups close patches together. In a second time the self-similarities search is performed for each group. By limiting the number of exhaustive searches we limit the memory occupation and the processing time. Results show that interesting complexity reduction can be achieved while keeping a good epitome quality (down to 18.08 % of the original memory occupation and 41.39%of the original processing time)."
abstract_short = ""
authors = ["M. Alain", "C. Guillemot", "D. Thoreau", "P. Guillotel"]
date = "2014-05-09"
highlight = true
image_preview = ""
math = true
publication = "European Signal Processing Conference"
publication_short = "EUSIPCO 2014"
publication_types = ["1"]
selected = false
title = "Clustering-based methods for fast epitome generation"
url_code = ""
url_dataset = ""
url_pdf = "pdf/Fast_epitome_EUSIPCO_2014.pdf"
url_project = ""
url_slides = ""
url_video = ""

[[url_custom]]
name = "BibTex"
url = "bib/AlainEUSIPCO2014.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "http://ieeexplore.ieee.org/document/6952021/"

[[url_custom]]
name = "INRIA"
url = "https://www.irisa.fr/temics/demos/clusteringBasedFastEpitome/clusteringBasedFastEpitome.html"

[header]
image = ""
caption = ""

+++


## Context and Goal

The concept of epitome was first introduced by Jojic et al. as the condensed representation (meaning its size is only a fraction of the original size) of an image containing the essence of its the textural properties. This original epitomic model is based on a patch-based probabilistic approach, and has different applications in segmentation, denoising, recognition, indexing or texture synthesis.  
Several epitomic models have been since proposed, such as the factorized representation of Wang et al. dedicated to texture mapping, or its extension designed for image coding purposes by Chérigui et al. The epitome is in this case the union of epitome charts which are pieces of repeatable textures found in the image. The search for self-similar or repeatable texture patterns, based on the KLT or a block matching (BM) algorithm, is known to be memory and time consuming.  
In this work, we propose a clustering-based technique to reduce the self-similarities search complexity.

## Approach

### Epitome generation

We summarize here the epitome generation process as proposed by Chérigui et al, in which the input image $I$ is factored in an epitome $E$ and an assignation map $\phi$. The input image is divided into a regular grid of non-overlapping blocks $B_i$ (block-grid) and each block will be reconstructed from an epitome patch. The epitome itself is composed of disjoint texture pieces called "epitome chart" (see Fig. 1). The assignation map links the patches from the epitome to the input image blocks. For more detailed explanations, see the papers listed [at the end of this page.](#references)

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterEptm_files/eptm_rec_Foreman.png" caption="Epitome of a Foreman frame (left) and the corresponding reconstruction (right)." >}}

#### Exhaustive self-similarities search

The method first proceeds by finding the self-similarities among the image. The goal of this step is to find for each non-overlapping block in the input image a list of matching patches such that the mean square error (MSE) between a block and its matching patches is below a matching threshold $\varepsilon_M$. This parameter eventually determines the size of the epitome. The matching patches are found through exhaustive search in the pixel-grid (see Fig. 2), and the assignation map $\phi$ is composed of translation parameters.
$$ \forall B\_i \in I, ML(B\_i) = \{M\_{i,0},M\_{i,1},\dots}, s.t. \forall j, MSE(B\_i,M\_{i,j}) \leq \varepsilon_M$$

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterEptm_files/ExhaustiveSearch.png" caption="Exhaustive self-similarities search." >}}


#### Epitome generation

The epitome charts are generated based on an iterative process. candidate patches used to initialize or grow the epitome charts are found by reversing the lists of matching patches obtained at the previous step. The selection of the best candidate is then performed based on a rate-distortion optimization (RDO) criterion, which minimizes the error between the input image $I$ and the image $I'$ as well as the size of the epitome. This criterion is summarized in the equation below, where $R(E)$ represents the size of the epitome estimated as the number of pixels. $$ (E, \phi) = argmin(MSE(I,I') + \lambda R(E))$$


{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterEptm_files/ECextensionStep.png" caption="Iterative epitome chart extension." >}}

### Clustering-based methods for fast self-similarities search

We propose two methods to reduce the complexity of the self-similarities search compared to the exhaustive search. The main idea is to group together similar non-overlapping blocks. The lists of matchnig patches are then computed for the group of blocks instead of each block separately. The similarity for grouping non-overlapping blocks is characterized by an assignation threshold $\varepsilon_A$, which is smaller than $\varepsilon_M$. Thus we define $\varepsilon_A$ _via_ a coefficient $\alpha_A$ such that $\varepsilon_A = \alpha_A * \varepsilon_M, 0 \leq \alpha_A < 1$.

#### List-based method

This method was designed to obtain a simple grouping of similar non-overlapping blocks and follows the steps below:

*   For each block $B_i$, find all blocks whose distance is below the assignation threshold $\varepsilon_A$. The association of $B_i$ and such blocks form a potential list $PL(B_i)$.
*   Find the potential list $PL_{opt}$ with the highest cardinal. This potential list is set as an actual list $AL$. Blocks in $AL$ are removed from the other potential lists they may belong to. If the block $B$ used to compute a potential list $PL(B)$ is removed from this list, this potential list no longer exists and is simply not considered in future iterations.
*   The previous step is iterated until all blocks belong to an actual list.

Finally for each actual list $AL(B_i)$ we determine a match list $ML(B_i) = \{M\_{i,0}, M\_{i,1}, \dots\}$ obtained through an exhaustive search in the pixel-grid. The list is computed with respect to $B_i$ but is then used by all blocks in $AL(B_i)$ for the epitome generation step. To satisfy the constraint that all the blocks have a reconstruction error inferior to $\varepsilon_M$, the blocks different from $B_i$ in the list $AL(B_i)$ only use a subset of $ML(B_i)$ defined as: $$ \{M \in ML(B_i) | D(B_i,M) \leq \varepsilon_M - \varepsilon_A\}$$

#### Threshold-based clustering

This method proceeds as follows:

*   A block $B_0$ is randomly selected and used to initialize the first cluster $C_0$.
*   For every block $B$ not assigned to a cluster, compute its distance to the centroid of all existing clusters. If all distances are higher than the assignation threshold $\varepsilon_A$, initialize a new cluster with $B$ as a seed. Otherwise assign $B$ to the closest cluster and recompute the centroid of this cluster as the average of all blocks in the cluster.
*   As a result, all blocks are assigned to a cluster. For every cluster, recompute the distances between the cluster blocks and the centroid. If a block $B$ is found to have a distance to the centroid superior to $\varepsilon_A$, it is considered as a singularity and remove from the cluster. $B$ is then used as a seed to initialize a new cluster.

For each cluster $C_i$ a match list $ML(B_i)$ is then computed through an exhaustive search in the pixel-grid, with respect to the block $B_i$ closest to the centroid. Except for the block $B_i$, all blocks in $C_i$ will use approximate matches. As for the previous grouping method, we want to ensure that all blocks have a reconstruction error inferior to $\varepsilon_M$. The blocks different from $B_i$ thus only use a subset of $ML(B_i)$, as defined in in the equation above.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterEptm_files/clusteringStep.png" caption="Two steps clusterring-based self-similarities search." >}}

## Experimental Results

Experiments were conducted on a set of 4 images: a frame extracted from the Foreman sequence (CIF), Lena ($512 \times 512$), City ($1280 \times 720$) and Calendar ($1280 \times 720$). The size of the blocks is set to $8 \times 8$.  
First tests were carried out with $\varepsilon_M = \{3.0, 5.0, 10.0, 15.0\}$. The parameter $\alpha_A$ was here set to $0.5$. Results are displayed in Table 1. Best results between list-based or cluster-based methods are displayed in bold font. The complexity reduction is assessed by the percentage of the optimized memory occupation over the original one, and the optimized method processing time over the original one. Two processing times are displayed: the self-similarities search time, which is the algorithm step actually optimized, and the complete epitome generation time.  
The memory occupation is prohibitive for images City and Calendar when $\varepsilon_M = 15.00$ with the original method. This shows a very important limitation of the full search method for high resolution images. Because of this, comparative results can not be displayed, but the epitome can be still generated when using optimized methods.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 1 - Memory occupation and computation time % with respect to original method, depending on $\varepsilon_M$, with $\alpha_A = 0.5$</caption>

<tbody>

<tr>

<td rowspan="2">Image</td>

<td rowspan="2">$\varepsilon_M$</td>

<td colspan="3">List-based method</td>

<td colspan="3">Cluster-based method</td>

</tr>

<tr>

<td>Memory load (%)</td>

<td>Search time (%)</td>

<td>Total time (%)</td>

<td>Memory load (%)</td>

<td>Search time (%)</td>

<td>Total time (%)</td>

</tr>

<tr>

<td rowspan="4">Foreman</td>

<td>3.0</td>

<td>50.18</td>

<td>68.62</td>

<td>73.93</td>

<th>47.85</th>

<th>67.31</th>

<th>70.15</th>

</tr>

<tr>

<td>5.0</td>

<td>49.54</td>

<td>60.72</td>

<th>60.12</th>

<th>45.22</th>

<th>55.80</th>

<td>61.88</td>

</tr>

<tr>

<td>10.0</td>

<td>25.00</td>

<td>32.65</td>

<th>41.39</th>

<th>19.06</th>

<th>28.58</th>

<td>50.36</td>

</tr>

<tr>

<td>15.0</td>

<td>18.08</td>

<td>21.61</td>

<th>42.37</th>

<th>14.59</th>

<th>18.00</th>

<td>55.25</td>

</tr>

<tr>

<td rowspan="4">Lena</td>

<td>3.0</td>

<td>98.18</td>

<td>75.54</td>

<td>78.92</td>

<th>96.81</th>

<th>69.05</th>

<th>70.13</th>

</tr>

<tr>

<td>5.0</td>

<td>63.61</td>

<td>61.00</td>

<th>65.24</th>

<th>48.28</th>

<th>56.12</th>

<td>66.19</td>

</tr>

<tr>

<td>10.0</td>

<td>29.98</td>

<td>37.49</td>

<th>51.92</th>

<th>23.66</th>

<th>31.60</th>

<td>55.74</td>

</tr>

<tr>

<td>15.0</td>

<th>19.96</th>

<th>23.09</th>

<th>59.69</th>

<td>21.64</td>

<td>23.56</td>

<td>64.48</td>

</tr>

<tr>

<td rowspan="3">City</td>

<td>3.0</td>

<td>60.54</td>

<th>66.75</th>

<th>65.27</th>

<th>55.85</th>

<td>68.62</td>

<td>69.25</td>

</tr>

<tr>

<td>5.0</td>

<td>60.71</td>

<td>64.165</td>

<td>64.160</td>

<th>56.47</th>

<th>62.48</th>

<th>62.80</th>

</tr>

<tr>

<td>10.0</td>

<td>51.47</td>

<td>48.07</td>

<td>60.07</td>

<th>48.18</th>

<th>47.06</th>

<th>59.75</th>

</tr>

<tr>

<td rowspan="3">Calendar</td>

<td>3.0</td>

<td>84.66</td>

<th>68.36</th>

<td>66.44</td>

<th>80.69</th>

<td>70.36</td>

<td>68.02</td>

</tr>

<tr>

<td>5.0</td>

<td>48.43</td>

<td>54.76</td>

<th>58.83</th>

<th>42.08</th>

<th>53.25</th>

<td>59.94</td>

</tr>

<tr>

<td>10.0</td>

<th>28.33</th>

<th>32.58</th>

<th>52.97</th>

<td>53.98</td>

<td>42.43</td>

<td>57.91</td>

</tr>

</tbody>

</table>

The quality of the epitome produced is assessed by the reconstructed image quality. The graphs representing the reconstructed image PSNR as a function of the epitome size are displayed in Fig. 5. For all images, whatever the epitome generation method, the curves are almost identical. The two proposed methods can thus reduce complexity while keeping the same epitome quality.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterEptm_files/rec_graph.png" caption="Reconstruction performances depending on $\varepsilon_M$." >}}

Complexity results for different values of $\alpha_A$ are displayed in Table 2, with $\varepsilon_M = 10.00$. These results illustrates the behavior of the proposed methods, which can reduce drastically the complexity when allowing important approximations. However, when evaluating average reconstruction performances (see Fig. 6), we can see that it has a negative impact, as it can increase the epitome size while decreasing the reconstruction PSNR.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 2 - Memory occupation and computation time % with respect to original method, depending on $\alpha_A$, with $\varepsilon_M = 10.0$</caption>

<tbody>

<tr>

<td rowspan="2">Image</td>

<td rowspan="2">$\alpha_A$</td>

<td colspan="3">List-based method</td>

<td colspan="3">Cluster-based method</td>

</tr>

<tr>

<td>Memory load (%)</td>

<td>Search time (%)</td>

<td>Total time (%)</td>

<td>Memory load (%)</td>

<td>Search time (%)</td>

<td>Total time (%)</td>

</tr>

<tr>

<td rowspan="3">Foreman</td>

<td>0.25</td>

<td>70.66</td>

<td>53.17</td>

<td>61.51</td>

<th>67.86</th>

<th>51.42</th>

<th>58.41</th>

</tr>

<tr>

<td>0.50</td>

<td>25.00</td>

<td>32.65</td>

<th>41.39</th>

<th>19.06</th>

<th>28.58</th>

<td>50.36</td>

</tr>

<tr>

<td>0.75</td>

<td>9.58</td>

<td>21.94</td>

<th>24.74</th>

<th>7.32</th>

<th>19.96</th>

<td>46.74</td>

</tr>

<tr>

<td rowspan="3">Lena</td>

<td>0.25</td>

<td>79.99</td>

<td>60.93</td>

<td>72.73</td>

<th>70.13</th>

<th>56.41</th>

<th>65.69</th>

</tr>

<tr>

<td>0.50</td>

<td>29.98</td>

<td>37.49</td>

<th>51.92</th>

<th>23.66</th>

<th>31.60</th>

<td>55.74</td>

</tr>

<tr>

<td>0.75</td>

<th>9.03</th>

<th>23.27</th>

<th>26.57</th>

<td>15.91</td>

<td>25.48</td>

<td>53.73</td>

</tr>

<tr>

<td rowspan="3">City</td>

<td>0.25</td>

<td>86.30</td>

<th>64.06</th>

<th>67.54</th>

<th>84.09</th>

<td>63.30</td>

<td>66.99</td>

</tr>

<tr>

<td>0.50</td>

<td>51.47</td>

<td>48.07</td>

<th>60.07</th>

<th>48.18</th>

<th>47.06</th>

<td>59.75</td>

</tr>

<tr>

<td>0.75</td>

<th>19.46</th>

<th>33.84</th>

<th>42.41</th>

<td>38.17</td>

<td>40.90</td>

<td>58.83</td>

</tr>

<tr>

<td rowspan="3">Calendar</td>

<td>0.25</td>

<td>69.76</td>

<td>51.43</td>

<td>65.30</td>

<th>65.85</th>

<th>49.95</th>

<td>66.65</td>

</tr>

<tr>

<td>0.50</td>

<th>28.33</th>

<th>32.58</th>

<th>52.97</th>

<td>53.98</td>

<td>42.43</td>

<td>57.91</td>

</tr>

<tr>

<td>0.75</td>

<th>10.13</th>

<th>22.69</th>

<th>29.61</th>

<td>48.35</td>

<td>36.86</td>

<td>57.94</td>

</tr>

</tbody>

</table>

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterEptm_files/Average_rec_graph_zoom_alpha.png" caption="Reconstruction performances depending on $\alpha_A$." >}}

## Applications

The concept of epitome presented here was used in different applications such as [still image coding](https://www.scss.tcd.ie/~alainm/publication/epitome_inpainting_with_in_loop_residue_coding_for_image_compression/) and [scalable image coding](https://www.scss.tcd.ie/~alainm/publication/scalable_image_coding_based_on_epitomes/).

## References

*   Nebojsa Jojic, Brendan J. Frey, Anitha Kannan, **Epitomic analysis of appearance and shape**, _ICCV 2003._ [[PDF]](http://research.microsoft.com/en-us/um/people/jojic/epitome/JojicFreyKannan_iccv03.pdf) [[Web]](http://research.microsoft.com/en-us/um/people/jojic/epitome.htm)
*   Huamin Wang, Yonatan Wexler, Eyal Ofek, Hugues Hoppe, **Factoring repeated content within and among images**, _SIGGRAPH 2008._ [[PDF]](http://research.microsoft.com/en-us/um/people/hoppe/factorimage.pdf) [[Web]](http://research.microsoft.com/en-us/um/people/hoppe/proj/factorimage)
*   Safa Cherigui, [Christine Guillemot](http://www.irisa.fr/temics/staff/guillemot/), [Dominique Thoreau](http://www.technicolor.com/en/dominique-thoreau), [Philippe Guilltotel](http://www.technicolor.com/en/philippe-guillotel) and [Patrick Perez](http://www.technicolor.com/en/patrick-perez), **Epitome-based image compression using translational sub-pel mapping**, _MMSP 2011._ [[PDF]](https://hal.inria.fr/hal-00994418/document)

