# ViDDAR: Vision Language Model-based Detrimental Content Detection for Augmented Reality
This repository is for IEEE VR 2025 submission - ViDDAR: Vision Language Model-based Detrimental Content Detection for Augmented Reality. It contains download links and the introduction of our collected datasets.

## 1. Overview

ViDDAR (Vision Language Model-based Detrimental content Detector for Augmented Reality) is a novel system designed to detect detrimental virtual content in AR environments. Virtual content in AR often aims to enhance user experiences, but if poorly designed or placed, it can obstruct critical real-world information or cause confusion, impairing the user's ability to interpret the scene.

ViDDAR addresses this issue by leveraging Vision Language Models (VLMs) and other SOTA deep learning-based models to identify and evaluate two types of detrimental content in AR:

 * **Obstruction Attacks**: Virtual objects that block important real-world elements, making them difficult for users to see or interact with.
 * **Confusion Attacks**: Virtual objects that mislead users about the function or meaning of real-world objects, potentially causing misunderstandings.
   
The ViDDAR system operates using an end-edge-cloud architecture to balance performance and latency:

 * **AR Device**: Captures real-world scenes and overlays virtual content. It sends raw and augmented images to the edge server for processing.
 * **Edge Server**: Uses multi-modal object detection and segmentation to analyze images and detect detrimental content in real-time.
 * **Cloud Server**: Hosts the Vision Language Model (e.g., GPT-4o or LLaVA-next), which provides semantic understanding to identify key objects and evaluate potential obstruction or confusion.


<table align="center">
  <tr>
    <td align="center"><img src="image/diagram_obstruction.png" height="250" alt="System architecture of ViDDAR for obstruction detection"/></td>
    <td align="center"><img src="image/diagram_confusion.png" height="250" alt="System architecture of ViDDAR for confusion detection"/></td>
  </tr>
  <tr>
    <td align="center"><strong>Figure 1. System architecture of ViDDAR for obstruction detection</strong></td>
    <td align="center"><strong>Figure 2. System architecture of ViDDAR for confusion detection</strong></td>
  </tr>
</table>







## 2. Dataset

The dataset mainly consists of two parts: obstruction attack dataset and confusion attack dataset. The data can be found at: https://drive.google.com/drive/folders/1IkJ5jV3O6XXSyeb78IlBAa8HzuVrBF0A?usp=sharing

### 2.1 Obstruction Attack Dataset:

There are 306 (raw_img, ar_img) pairs in the dataset. Each raw image contains only 1 key object. There are 23 classes of key objects in total.




#### Data:

obstruction_raw_img: the raw images in the dataset.

obstruction_ar_img: the AR images in the dataset.

obstruction_key_object_mask: the binary masks of the key objects in the raw image. Each raw image contains only 1 key object.

obstruction_ar_content_mask: the binary mask of the augmented virtual content in the AR images.


#### Label: 
obstruction_labels.csv: contains two labels for each (raw_img, ar_img) pair: (1) the key object's name; (2) obstruction status (whether the key object is obstructed by virtual content in the AR image, "yes" for obstructed, "no" for no obstruction.)

<p align="center"><img src="image/obstruction_data_sample.png" width="580"\></p>
<p align="center"><strong>Figure 1. Overview of BiGuide design.</strong></p> 



### 2.2 Confusion Attack Dataset:

There are 114 (raw_img, ar_img) pairs in the dataset. Each image pair shows a scenario where virtual content is combined with real world object. There are 10 combinations accross the dataset.

#### Data: 

confusion_raw_img: the raw images in the dataset.

confusion_ar_img: the AR images in the dataset.

#### Label:
confusion_labels.csv: contains four labels for each (raw_img, ar_img) pair: (1) the alignment precision (1 for good, 0 for bad); (2) style similarity (1 for high, 2 for low); (3) functional misrepresentation (1 for likely, 0 for unlikely); (4) overall confusion likelihood (1 for high, 0 for low.)
