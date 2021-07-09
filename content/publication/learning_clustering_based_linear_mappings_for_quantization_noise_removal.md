+++
abstract = "This paper describes a novel scheme to reduce the quantization noise of compressed videos and improve the overall coding performances. The proposed scheme first consists in clustering noisy patches of the compressed sequence. Then, at the encoder side, linear mappings are learned for each cluster between the noisy patches and the corresponding source patches. The linear mappings are then transmitted to the decoder where they can be applied to perform de-noising. The method has been tested with the HEVC standard, leading to a bitrate saving of up to 9.63%."
abstract_short = ""
authors = ["M. Alain", "C. Guillemot", "D. Thoreau", "P. Guillotel"]
date = "2016-09-25"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Conference on Image Processing"
publication_short = "ICIP 2016"
publication_types = ["1"]
selected = false
title = "Learning clustering-based linear mappings for quantization noise removal"
url_code = ""
url_dataset = ""
url_pdf = "pdf/Clustering_based_denoising.pdf"
url_project = ""
url_slides = ""
url_video = ""

#[[url_custom]]
#name = "BibTex"
#url = "bib/AlainICIP16.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "http://ieeexplore.ieee.org/document/7533151/"

[[url_custom]]
name = "INRIA"
url = "http://www.irisa.fr/temics/demos/clusteringLinearMappingNoiseRemoval/clusteringLinearMappingNoiseRemoval.html"

[header]
image = "headers/clusteringLinearMappingNoiseRemoval.png"
caption = ""

+++

## Context and Goal

Modern video codecs such as HEVC rely on four main steps, which aim at reducing the redundancies of the signal. First, spatial and temporal redudancies are reduced through prediction tools. The prediction residue is then transformed to further reduce the inner correlations of the signal, and the transformed coefficients are then quantized to remove non-perceptible information. The quantized transformed coefficients are finally entropy coded to remove the remaining statistical redundancies. Because the quantization step is not revertible at the decoder side, the reconstructed frames are corrupted with a so-called quantization noise. The goal of this work is to improve the rate-distortion (RD) performances of existing compression schemes using a novel out-of-the-loop de-noising scheme.


## Approach

The proposed scheme is represented in Fig. 1, and consists in the following steps:

* At the encoder side:

    *   cluster the coded/decoded patches
    *   for each cluster, learn a projection function using multivariate linear regression between the coded/decoded patches and the corresponding source patches
    *   encode the projection function and transmit them to the decoder

* At the decoder side:

    *   decode the projection functions
    *   cluster the decoded patches, as it is performed at the encoder side
    *   for each cluster, apply the corresponding projection function to the decoded patches in order to obtain the de-noised patches

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterLM_files/proposed_scheme.png" caption="Proposed compression scheme using noise removal based on clustering and linear mapping learning." >}}

Alternatively, we propose a two steps scheme represented in Fig. 2, where a blind de-noising algorithm is first performed on the decoded frames, before applying the proposed mehtods.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterLM_files/two_steps_scheme.png" caption="Alternative two step schemes with first pass blind de-noising." >}}


### Selecting the number of clusters

Selecting the number of clusters K is crucial for the overall RD performances, as increasing K improves the de-noising performances, but also the bit-rate associated to the projection functions. We thus propose an adative method to select K, based on a rate-distortion optimization (RDO) criterion, which proceeds as follow:

*   At initialization, the full data set is considered as one cluster
*   Each cluster is then recursively split in 2 clusters if the RDO criterion (explained below) is satisfied, creating a binary tree structure
*   The procedure stops when no RDO criterion is satisfied, or a certain maximum tree depth is reached

To perform the exact same partitioning at the decoder, we then need to transmit the binary tree structure.  
The aforementioned RDO criterion can be computed for each cluster, first by estimating the distortion between the de-noised patches of the cluster and the corresponding source patches. The rate is then esitmated as the number of bits of the encoded projection function used to de-noise the patches. Thus, to decide if a cluster $C\_{n}$ is further divided into two clusters $C\_{n+1}$ and $C\_{n+2}$, we merely check the following condition on the associated rate distortion costs: $J\_{n+1} + J\_{n+2} < J\_n$. An example of binary tree structure obtained after recursive paritioning is given in Fig. 3.

{{< figure src="https://www.scss.tcd.ie/~alainm/img/clusterLM_files/BT_example.png" caption="Example of a cluster partition based on a binary tree structure and an RDO criterion. The clusters are recursively split to reach 4 clusters. The tree structure is described by only 5 bits." >}}

### Oracle clustering

We propose a so-called oracle clustering, which goal is to maximize the de-noising performances of the proposed scheme for a fixed number of clusters $K$. Formally, the oracle clustering solve the following problem:
$$\min\_C \sum\_{i=1 \dots K} \sum\_{x\_d,x\_s \in C\_i} || x\_s - \textbf{P}\_i x\_d || ^2 $$
where $x\_s$ and $x\_d$ are corresponding source and decoded patches respectively, and $\textbf{P}\_i$ is the projection function corresponding to the cluster $C\_i$.  
This oracle clustering is not reproducible at the decoder side, as it relies on the knowledge of the source patches, and thus can not be directly applied in the proposed scheme. However, it allows to define an upper bound on the performances.

| ![source image](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/Kimono_frm_1.png)   | ![compressed image](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/Kimono_frm_1_QP_37.png)  |
|------------------|---------------------|
|First frame of the Kimono source sequence. | First frame of the Kimono sequence encoded with HEVC at QP=37. Decoded PSNR = 37.95dB. |
| ![kmeans clustering] (https://www.scss.tcd.ie/~alainm/img/clusterLM_files/Kimono_frm_1_QP_37_kmeans.png)  | ![oracle clustering](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/Kimono_frm_1_QP_37_opt_cltr.png)  |
| K-means clustering (K=10) performed on non-overlapping 4x4 patches of the Kimono sequence encoded with HEVC at QP=37. Each color correspond to a cluster label. Corresponding de-noised PSNR = 38.07 dB.|  Oracle clustering (K=10) performed on non-overlapping 4x4 patches of the Kimono sequence encoded with HEVC at QP=37. Each color correspond to a cluster label. Corresponding de-noised PSNR = 41.26 dB. |


## Experimental Results

The sequences used in the experiment are presented in Table 1, and mainly consist in HEVC test sequences. The test sequences are processed per Group Of Pictures (GOP), where a GOP contains a number of frames equal to the frame rate (_i.e._ we have one GOP per second). The sequences are encoded with the HEVC test model HM (ver 15.0) using the Main profile in Random Access, with 4 values for the Quantization Parameter, QP=22, 27, 32, 37.

<table style="text-align: center; width: 60%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 1 - Test sequences</caption>

<tbody>

<tr>

<th>Sequence</th>

<th>Resolution</th>

<th>Frame count</th>

<th>Frame rate</th>

</tr>

<tr>

<td>City</td>

<td>1280x720</td>

<td>600</td>

<td>60</td>

</tr>

<tr>

<td>ParkScene</td>

<td>1920x1080</td>

<td>240</td>

<td>24</td>

</tr>

<tr>

<td>Tennis</td>

<td>1920x1080</td>

<td>240</td>

<td>24</td>

</tr>

<tr>

<td>Kimono</td>

<td>1920x1080</td>

<td>240</td>

<td>24</td>

</tr>

<tr>

<td>Cactus</td>

<td>1920x1080</td>

<td>500</td>

<td>50</td>

</tr>

<tr>

<td>Terrace</td>

<td>1920x1080</td>

<td>600</td>

<td>60</td>

</tr>

<tr>

<td>Basket</td>

<td>1920x1080</td>

<td>500</td>

<td>50</td>

</tr>

<tr>

<td>Ducks</td>

<td>1920x1080</td>

<td>500</td>

<td>50</td>

</tr>

<tr>

<td>PeopleOnStreet</td>

<td>2560x1600</td>

<td>150</td>

<td>30</td>

</tr>

<tr>

<td>Traffic</td>

<td>2560x1600</td>

<td>150</td>

<td>30</td>

</tr>

</tbody>

</table>

We show in Table 2 the RD performances of our method (without first pass de-noising, see Fig. 1) for each GOP of the test sequences, performed with fixed number of clusters K=10.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2"><caption>Table 2 - RD performances per GOP of K-means clustering with a fixed number of clusters K=10 (Bjontegaard bit-rate gains with respect to HEVC)</caption>

<tbody>

<tr>

<th>GOP</th>

<th>City</th>

<th>Park Scene</th>

<th>Tennis</th>

<th>Kimono</th>

<th>Cactus</th>

<th>Terrace</th>

<th>Basket</th>

<th>Ducks</th>

<th>People On Street</th>

<th>Traffic</th>

<th>Average</th>

</tr>

<tr>

<th>1</th>

<td>-2.31</td>

<td>0.12</td>

<td>-0.06</td>

<td>-0.13</td>

<td>-1.16</td>

<td>-5.38</td>

<td>-0.83</td>

<td>-2.32</td>

<td>-2.54</td>

<td>-1.29</td>

<td>-1.59</td>

</tr>

<tr>

<th>2</th>

<td>-1.76</td>

<td>0.15</td>

<td>0.09</td>

<td>-0.13</td>

<td>-1.22</td>

<td>-7.14</td>

<td>-0.43</td>

<td>-1.81</td>

<td>-2.55</td>

<td>-1.23</td>

<td>-1.60</td>

</tr>

<tr>

<th>3</th>

<td>-1.96</td>

<td>0.09</td>

<td>0.18</td>

<td>-0.20</td>

<td>-0.88</td>

<td>-8.62</td>

<td>-0.87</td>

<td>-1.02</td>

<td>-2.54</td>

<td>-1.22</td>

<td>-1.70</td>

</tr>

<tr>

<th>4</th>

<td>-1.74</td>

<td>0.18</td>

<td>0.10</td>

<td>-0.24</td>

<td>-0.81</td>

<td>-11.69</td>

<td>-0.74</td>

<td>-1.16</td>

<td>-2.60</td>

<td>-1.18</td>

<td>-1.99</td>

</tr>

<tr>

<th>5</th>

<td>-0.96</td>

<td>0.30</td>

<td>0.10</td>

<td>-0.19</td>

<td>-1.05</td>

<td>-12.15</td>

<td>-0.65</td>

<td>-1.20</td>

<td>-2.58</td>

<td>-1.31</td>

<td>-1.97</td>

</tr>

<tr>

<th>6</th>

<td>-1.90</td>

<td>0.47</td>

<td>1.60</td>

<td>0.35</td>

<td>-1.20</td>

<td>-10.05</td>

<td>-0.43</td>

<td>-1.61</td>

<td>-1.60</td>

</tr>

<tr>

<th>7</th>

<td>-1.59</td>

<td>0.48</td>

<td>1.45</td>

<td>1.22</td>

<td>-1.11</td>

<td>-8.49</td>

<td>-0.51</td>

<td>-2.01</td>

<td>-1.32</td>

</tr>

<tr>

<th>8</th>

<td>-1.98</td>

<td>0.50</td>

<td>1.05</td>

<td>1.42</td>

<td>-1.34</td>

<td>-7.53</td>

<td>-0.71</td>

<td>-2.36</td>

<td>-1.37</td>

</tr>

<tr>

<th>9</th>

<td>-1.84</td>

<td>0.59</td>

<td>0.84</td>

<td>1.90</td>

<td>-1.03</td>

<td>-6.73</td>

<td>-0.74</td>

<td>-2.49</td>

<td>-1.19</td>

</tr>

<tr>

<th>10</th>

<td>-1.92</td>

<td>0.97</td>

<td>0.77</td>

<td>2.54</td>

<td>-0.91</td>

<td>-6.79</td>

<td>-0.49</td>

<td>-2.76</td>

<td>-1.07</td>

</tr>

<tr>

<th>Average</th>

<td>-1.81</td>

<td>0.38</td>

<td>0.08</td>

<td>0.43</td>

<td>-1.08</td>

<td>-8.28</td>

<td>-0.65</td>

<td>-1.88</td>

<td>-2.56</td>

<td>-1.26</td>

<td>-1.66</td>

</tr>

</tbody>

</table>

We show in Table 3 the RD performances of our method (without first pass de-noising, see Fig. 1) for each GOP of the test sequences, performed with the adaptive selection of the number of clusters (Kmax=16). In addition, we give in Table 4 the selected K values depending on the quantization parameter and averaged over all GOPs. We can see that the K values adapt to the sequence, reaching higher values for sequences with a higher resolution and/or frame rate. The K values also vary depending on QP, and lower values are selected at low bit-rate (high QP value).

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2"><caption>Table 3 - RD performances per GOP of K-means clustering with the adaptive K selection (Kmax=16) (Bjontegaard bit-rate gains with respect to HEVC)</caption>

<tbody>

<tr>

<th>GOP</th>

<th>City</th>

<th>Park Scene</th>

<th>Tennis</th>

<th>Kimono</th>

<th>Cactus</th>

<th>Terrace</th>

<th>Basket</th>

<th>Ducks</th>

<th>People On Street</th>

<th>Traffic</th>

<th>Average</th>

</tr>

<tr>

<th>1</th>

<td>-2.76</td>

<td>-0.69</td>

<td>-0.90</td>

<td>-1.32</td>

<td>-1.12</td>

<td>-5.25</td>

<td>-1.10</td>

<td>-2.39</td>

<td>-2.57</td>

<td>-1.44</td>

<td>-1.96</td>

</tr>

<tr>

<th>2</th>

<td>-2.31</td>

<td>-0.67</td>

<td>-0.72</td>

<td>-1.35</td>

<td>-1.29</td>

<td>-6.83</td>

<td>-0.40</td>

<td>-1.82</td>

<td>-2.58</td>

<td>-1.39</td>

<td>-1.93</td>

</tr>

<tr>

<th>3</th>

<td>-2.45</td>

<td>-0.63</td>

<td>-0.78</td>

<td>-1.36</td>

<td>-0.89</td>

<td>-8.86</td>

<td>-0.98</td>

<td>-1.08</td>

<td>-2.59</td>

<td>-1.35</td>

<td>-2.10</td>

</tr>

<tr>

<th>4</th>

<td>-1.66</td>

<td>-0.54</td>

<td>-0.82</td>

<td>-1.31</td>

<td>-0.98</td>

<td>-11.58</td>

<td>-0.62</td>

<td>-1.24</td>

<td>-2.61</td>

<td>-1.35</td>

<td>-2.27</td>

</tr>

<tr>

<th>5</th>

<td>-1.84</td>

<td>-0.52</td>

<td>-0.72</td>

<td>-0.89</td>

<td>-1.11</td>

<td>-11.95</td>

<td>-0.76</td>

<td>-1.27</td>

<td>-2.63</td>

<td>-1.53</td>

<td>-2.32</td>

</tr>

<tr>

<th>6</th>

<td>-2.22</td>

<td>-0.48</td>

<td>-1.08</td>

<td>-0.85</td>

<td>-1.37</td>

<td>-9.90</td>

<td>-0.77</td>

<td>-1.71</td>

<td>-2.30</td>

</tr>

<tr>

<th>7</th>

<td>-1.90</td>

<td>-0.48</td>

<td>-1.91</td>

<td>-0.58</td>

<td>-1.25</td>

<td>-8.20</td>

<td>-0.68</td>

<td>-2.13</td>

<td>-2.14</td>

</tr>

<tr>

<th>8</th>

<td>-1.86</td>

<td>-0.40</td>

<td>-2.39</td>

<td>-0.58</td>

<td>-1.30</td>

<td>-7.23</td>

<td>-1.09</td>

<td>-2.47</td>

<td>-2.16</td>

</tr>

<tr>

<th>9</th>

<td>-2.51</td>

<td>-0.31</td>

<td>-1.77</td>

<td>-0.43</td>

<td>-1.19</td>

<td>-6.35</td>

<td>-0.88</td>

<td>-2.58</td>

<td>-2.00</td>

</tr>

<tr>

<th>10</th>

<td>-2.74</td>

<td>0.02</td>

<td>-2.52</td>

<td>0.29</td>

<td>-1.00</td>

<td>-6.47</td>

<td>-0.69</td>

<td>-2.84</td>

<td>-1.99</td>

</tr>

<tr>

<th>Average</th>

<td>-2.24</td>

<td>-0.47</td>

<td>-1.41</td>

<td>-0.94</td>

<td>-1.15</td>

<td>-8.08</td>

<td>-0.80</td>

<td>-1.96</td>

<td>-2.60</td>

<td>-1.42</td>

<td>-2.11</td>

</tr>

</tbody>

</table>

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2"><caption>Table 4 - Selected K values for the RDO adaptive selection of the number of clusters (Averaged over all GOPs)</caption>

<tbody>

<tr>

<th>QP</th>

<th>City</th>

<th>Park Scene</th>

<th>Tennis</th>

<th>Kimono</th>

<th>Cactus</th>

<th>Terrace</th>

<th>Basket</th>

<th>Ducks</th>

<th>People On Street</th>

<th>Traffic</th>

<th>Average</th>

</tr>

<tr>

<th>22</th>

<td>10.8</td>

<td>8.5</td>

<td>7.6</td>

<td>8.2</td>

<td>14.9</td>

<td>15.4</td>

<td>12.0</td>

<td>15.9</td>

<td>16.0</td>

<td>14.0</td>

<td>12.3</td>

</tr>

<tr>

<th>27</th>

<td>11.3</td>

<td>6.8</td>

<td>5.7</td>

<td>6.4</td>

<td>11.7</td>

<td>15.0</td>

<td>9.7</td>

<td>15.8</td>

<td>16.0</td>

<td>12.6</td>

<td>11.1</td>

</tr>

<tr>

<th>32</th>

<td>7.4</td>

<td>4.0</td>

<td>3.4</td>

<td>4.5</td>

<td>9.0</td>

<td>14.1</td>

<td>7.8</td>

<td>15.8</td>

<td>16.0</td>

<td>7.6</td>

<td>9.0</td>

</tr>

<tr>

<th>37</th>

<td>5.9</td>

<td>4.0</td>

<td>2.8</td>

<td>4.0</td>

<td>7.1</td>

<td>13.1</td>

<td>5.8</td>

<td>15.5</td>

<td>15.8</td>

<td>5.8</td>

<td>8.0</td>

</tr>

<tr>

<th>Average</th>

<td>8.9</td>

<td>5.8</td>

<td>4.9</td>

<td>5.8</td>

<td>10.7</td>

<td>14.4</td>

<td>8.8</td>

<td>15.8</td>

<td>16.0</td>

<td>10.0</td>

<td>10.1</td>

</tr>

</tbody>

</table>

We show in Table 5 the RD performances of the proposed two steps scheme (see Fig. 2), with a first pass VBM3D de-noising, for the first GOP of the test sequences, performed with the adaptive selection of the number of clusters (Kmax=16). In addition, we give in Table 6 the selected K values depending on the quantization parameter.

<table style="text-align: center; width: 40%;" border="1" cellpadding="2" cellspacing="2" align="center"><caption>Table 5 - RD performances of the two steps scheme with the adaptive K selection (Kmax=16) for the first GOP (Bjontegaard bit-rate gains with respect to HEVC)</caption>

<tbody>

<tr>

<th>Sequence</th>

<th>BD-rate</th>

</tr>

<tr>

<th>City</th>

<td>-3.24</td>

</tr>

<tr>

<th>Park Scene</th>

<td>-1.07</td>

</tr>

<tr>

<th>Tennis</th>

<td>-7.77</td>

</tr>

<tr>

<th>Kimono</th>

<td>-4.32</td>

</tr>

<tr>

<th>Cactus</th>

<td>-6.19</td>

</tr>

<tr>

<th>Terrace</th>

<td>-7.24</td>

</tr>

<tr>

<th>Basket</th>

<td>-3.80</td>

</tr>

<tr>

<th>Ducks</th>

<td>-4.13</td>

</tr>

<tr>

<th>People On Street</th>

<td>-9.63</td>

</tr>

<tr>

<th>Traffic</th>

<td>-5.43</td>

</tr>

<tr>

<th>Average</th>

<td>-5.28</td>

</tr>

</tbody>

</table>

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2"><caption>Table 6 - Selected K values for the two steps scheme with the RDO adaptive selection of the number of clusters (Averaged over all GOPs)</caption>

<tbody>

<tr>

<th>QP</th>

<th>City</th>

<th>Park Scene</th>

<th>Tennis</th>

<th>Kimono</th>

<th>Cactus</th>

<th>Terrace</th>

<th>Basket</th>

<th>Ducks</th>

<th>People On Street</th>

<th>Traffic</th>

<th>Average</th>

</tr>

<tr>

<th>22</th>

<td>15.0</td>

<td>12.0</td>

<td>9.0</td>

<td>7.0</td>

<td>16.0</td>

<td>16.0</td>

<td>11.0</td>

<td>16.0</td>

<td>16.0</td>

<td>15.0</td>

<td>13.3</td>

</tr>

<tr>

<th>27</th>

<td>15.0</td>

<td>8.0</td>

<td>7.0</td>

<td>6.0</td>

<td>13.0</td>

<td>16.0</td>

<td>11.0</td>

<td>16.0</td>

<td>16.0</td>

<td>12.0</td>

<td>12.0</td>

</tr>

<tr>

<th>32</th>

<td>10.0</td>

<td>6.0</td>

<td>6.0</td>

<td>6.0</td>

<td>12.0</td>

<td>16.0</td>

<td>9.0</td>

<td>16.0</td>

<td>15.0</td>

<td>13.0</td>

<td>10.9</td>

</tr>

<tr>

<th>37</th>

<td>9.0</td>

<td>4.0</td>

<td>5.0</td>

<td>4.0</td>

<td>11.0</td>

<td>15.0</td>

<td>5.0</td>

<td>16.0</td>

<td>15.0</td>

<td>6.0</td>

<td>9.0</td>

</tr>

<tr>

<th>Average</th>

<td>12.3</td>

<td>7.5</td>

<td>6.8</td>

<td>5.8</td>

<td>13.0</td>

<td>15.8</td>

<td>9.0</td>

<td>16.0</td>

<td>15.5</td>

<td>11.5</td>

<td>11.3</td>

</tr>

</tbody>

</table>

Finally, we show in Table 7 the upper bound on the RD performances obtained with the oracle clustering.

<table style="text-align: center; width: 100%;" border="1" cellpadding="2" cellspacing="2"><caption>Table 7 - Upper bound on the RD performances per GOP using the oracle clustering with a fixed number of clusters K=10 (Bjontegaard bit-rate gains with respect to HEVC)</caption>

<tbody>

<tr>

<th>GOP</th>

<th>City</th>

<th>Park Scene</th>

<th>Tennis</th>

<th>Kimono</th>

<th>Cactus</th>

<th>Terrace</th>

<th>Basket</th>

<th>Ducks</th>

<th>People On Street</th>

<th>Traffic</th>

<th>Average</th>

</tr>

<tr>

<th>1</th>

<td>-28.85</td>

<td>-22.38</td>

<td>-30.48</td>

<td>-40.90</td>

<td>-23.28</td>

<td>-29.93</td>

<td>-32.60</td>

<td>-31.03</td>

<td>-23.11</td>

<td>-25.35</td>

<td>-28.79</td>

</tr>

<tr>

<th>2</th>

<td>-28.34</td>

<td>-22.40</td>

<td>-30.39</td>

<td>-42.10</td>

<td>-24.62</td>

<td>-34.49</td>

<td>-29.80</td>

<td>-28.40</td>

<td>-23.15</td>

<td>-25.52</td>

<td>-28.92</td>

</tr>

<tr>

<th>3</th>

<td>-28.35</td>

<td>-21.86</td>

<td>-30.61</td>

<td>-41.10</td>

<td>-24.89</td>

<td>-41.78</td>

<td>-30.62</td>

<td>-18.31</td>

<td>-23.07</td>

<td>-25.31</td>

<td>-28.59</td>

</tr>

<tr>

<th>4</th>

<td>-29.20</td>

<td>-21.43</td>

<td>-30.92</td>

<td>-40.77</td>

<td>-26.09</td>

<td>-48.57</td>

<td>-27.25</td>

<td>-16.72</td>

<td>-23.88</td>

<td>-25.68</td>

<td>-29.05</td>

</tr>

<tr>

<th>5</th>

<td>-28.89</td>

<td>-21.07</td>

<td>-30.34</td>

<td>-40.85</td>

<td>-25.08</td>

<td>-46.06</td>

<td>-29.78</td>

<td>-16.08</td>

<td>-23.07</td>

<td>-25.65</td>

<td>-28.69</td>

</tr>

<tr>

<th>6</th>

<td>-29.43</td>

<td>-21.50</td>

<td>-44.94</td>

<td>-38.14</td>

<td>-24.65</td>

<td>-39.84</td>

<td>-31.07</td>

<td>-18.51</td>

<td>-31.01</td>

</tr>

<tr>

<th>7</th>

<td>-29.19</td>

<td>-21.66</td>

<td>-45.89</td>

<td>-25.38</td>

<td>-24.21</td>

<td>-38.70</td>

<td>-29.48</td>

<td>-20.69</td>

<td>-29.40</td>

</tr>

<tr>

<th>8</th>

<td>-29.08</td>

<td>-21.71</td>

<td>-46.38</td>

<td>-25.24</td>

<td>-24.71</td>

<td>-37.85</td>

<td>-30.36</td>

<td>-22.64</td>

<td>-29.75</td>

</tr>

<tr>

<th>9</th>

<td>-28.89</td>

<td>-21.37</td>

<td>-45.92</td>

<td>-25.17</td>

<td>-24.53</td>

<td>-35.55</td>

<td>-27.57</td>

<td>-23.33</td>

<td>-29.04</td>

</tr>

<tr>

<th>10</th>

<td>-29.01</td>

<td>-21.24</td>

<td>-46.14</td>

<td>-16.37</td>

<td>-12.72</td>

<td>-42.21</td>

<td>-21.39</td>

<td>-24.99</td>

<td>-26.76</td>

</tr>

<tr>

<th>Average</th>

<td>-28.92</td>

<td>-21.66</td>

<td>-38.20</td>

<td>-33.60</td>

<td>-23.48</td>

<td>-39.50</td>

<td>-28.99</td>

<td>-22.07</td>

<td>-23.26</td>

<td>-25.50</td>

<td>-28.52</td>

</tr>

</tbody>

</table>

We display below a summary of the RD performances of the different versions of the proposed scheme, in the form of RD curves for the first GOP of each sequence.

| ![City RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_city.png)  | ![Park Scene RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_park_scene.png)   |
|------------------|-----------------------|
| RD performances for the first GOP of the City sequence. | RD performances for the first GOP of the Park Scene sequence. |
| ![Tennis RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_tennis.png)  | ![Kimono RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_kimono.png)   |
| RD performances for the first GOP of the Tennis sequence. |  RD performances for the first GOP of the Kimono sequence. |
| ![Cactus RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_cactus.png)   | ![Terrace RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_terrace.png)     |
| RD performances for the first GOP of the Cactus sequence. | RD performances for the first GOP of the Terrace sequence.   |
| ![Basket RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_basket.png)  | ![Ducks RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_ducks.png)   |
| RD performances for the first GOP of the Basket sequence. | RD performances for the first GOP of the Ducks sequence.  |
| ![People On Street RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_people_on_street.png)  | ![Traffic RD curve](https://www.scss.tcd.ie/~alainm/img/clusterLM_files/RD_curve_traffic.png)     |
| RD performances for the first GOP of the People On Street sequence. |RD performances for the first GOP of the Traffic sequence.   | 

## References

* Kostadin Dabov, Alessandro Foi, Karen Egiazarian, **Video denoising by sparse 3D transform-domain collaborative filtering**, _EUSIPCO 2007._ [[PDF]](http://www.cs.tut.fi/~foi/GCF-BM3D/VBM3D_EUSIPCO_2007.pdf)
