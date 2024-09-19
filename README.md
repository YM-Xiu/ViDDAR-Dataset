# ViDDAR-Dataset
This is the dataset of IEEE VR 2025 submission - ViDDAR: Vision Language Model-based Detrimental Content Detection for Augmented Reality.

## Dataset Description:

The dataset mainly consists of two parts: obstruction attack dataset and confusion attack dataset. The data can be found at: https://drive.google.com/drive/folders/1IkJ5jV3O6XXSyeb78IlBAa8HzuVrBF0A?usp=sharing

### Obstruction Attack Dataset:

There are 306 (raw_img, ar_img) pairs in the dataset. Each raw image contains only 1 key object. There are 23 classes of key objects in total.

#### Data:

obstruction_raw_img: the raw images in the dataset.

obstruction_ar_img: the AR images in the dataset.

obstruction_key_object_mask: the binary masks of the key objects in the raw image. Each raw image contains only 1 key object.

obstruction_ar_content_mask: the binary mask of the augmented virtual content in the AR images.


#### Label: 
obstruction_labels.csv: contains two labels for each (raw_img, ar_img) pair: (1) the key object's name; (2) obstruction status (whether the key object is obstructed by virtual content in the AR image, "yes" for obstructed, "no" for no obstruction.)


### Confusion Attack Dataset:

There are 114 (raw_img, ar_img) pairs in the dataset. Each image pair shows a scenario where virtual content is combined with real world object. There are 10 combinations accross the dataset.

#### Data: 

confusion_raw_img: the raw images in the dataset.

confusion_ar_img: the AR images in the dataset.

#### Label:
confusion_labels.csv: contains four labels for each (raw_img, ar_img) pair: (1) the alignment precision (1 for good, 0 for bad); (2) style similarity (1 for high, 2 for low); (3) functional misrepresentation (1 for likely, 0 for unlikely); (4) overall confusion likelihood (1 for high, 0 for low.)
