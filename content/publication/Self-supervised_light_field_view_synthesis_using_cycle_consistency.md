+++
abstract = "High angular resolution is advantageous for practical applications of light fields. In order to enhance the angular resolution of light fields, view synthesis methods can be utilized to generate dense intermediate views from sparse light field input. Most successful view synthesis methods are learning-based approaches which require a large amount of training data paired with ground truth. However, collecting such large datasets for light fields is challenging compared to natural images or videos. To tackle this problem, we propose a self-supervised light field view synthesis framework with cycle consistency. The proposed method aims to transfer prior knowledge learned from high quality natural video datasets to the light field view synthesis task, which reduces the need for labeled light field data. A cycle consistency constraint is used to build bidirectional mapping enforcing the generated views to be consistent with the input views. Derived from this key concept, two loss functions, cycle loss and reconstruction loss, are used to fine-tune the pre-trained model of a state-of-the-art video interpolation method. The proposed method is evaluated on various datasets to validate its robustness, and results show it not only achieves competitive performance compared to supervised fine-tuning, but also outperforms state-of-the-art light field view synthesis methods, especially when generating multiple intermediate views. Besides, our generic light field view synthesis framework can be adopted to any pre-trained model for advanced video interpolation."
abstract_short = ""
authors = ["Y. Yang.", "M. Alain", "A. Smolic"]
date = "2020-09-21"
highlight = true
image_preview = ""
math = true
publication = "IEEE International Workshop on Multimedia Signal Processing"
publication_short = "MMSP 2020"
publication_types = ["1"]
selected = false
title = "Self-supervised light field view synthesis using cycle consistency"
url_code = ""
url_dataset = ""
url_pdf = "https://arxiv.org/pdf/2008.05084.pdf"
url_project = ""
url_slides = ""
url_video = ""

#[[url_custom]]
#name = "BibTex"
#url = "bib/AlainICIP2018.bib"

[[url_custom]]
name = "IEEE Xplore"
url = "http://ieeexplore.ieee.org/document/9287105/"

[[url_custom]]
name = "V-SENSE"
url = "https://v-sense.scss.tcd.ie/research/self-supervised-light-field-view-synthesis-using-cycle-consistency/"

[header]
image = "headers/ECCV_Figures-Page-1_LF_intro-1140x528.png"
caption = ""

+++

<h2>Implementation</h2>

<p>Please watch our official repo on <a href="https://github.com/V-Sense" target="_blank" rel="noreferrer noopener">Github</a>, code will be released soon.</p>
