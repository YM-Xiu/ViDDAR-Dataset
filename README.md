# ViDDAR-Dataset
This is the dataset of IEEE VR 2025 submission - ViDDAR: Vision Language Model-based Detrimental Content Detection for Augmented Reality.

## Dataset Description:

The dataset mainly consists of two parts: obstruction attack dataset and confusion attack dataset. The data can be found at: 

### Obstruction Attack Dataset:

#### Data:

obstruction_raw_img: the raw images in the dataset.

obstruction_ar_img: the AR images in the dataset.

obstruction_key_object_mask: the binary masks of the key objects in the raw image. Each raw image contains only 1 key object.

obstruction_ar_content_mask: the binary mask of the augmented virtual content in the AR images.


#### Label: 
obstruction_labels.csv: contains two labels for each (raw_img, ar_img) pair: (1) the key object's name; (2) obstruction status (whether the key object is obstructed by virtual content in the AR image.)
