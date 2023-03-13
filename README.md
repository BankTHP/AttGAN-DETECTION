# Transferability of CNN models for GAN-generated Face Detection

Classifier สำหรับการ Detect fake image from AttGAN  

## Dataset
The dataset utilized in the experiment is the Labeled Face in a Wild (LFW) dataset, which consists of 5721 photos of people aggregating 13143 images. The number of photographs in each attribute is summarized as follows.

-   13143 images
-   5721 people
-   1680 people with two or more images
-   40+ Attribute 
	> [Dataset LFW](http://vis-www.cs.umass.edu/lfw/),

| Attribute | Without Attribute | With Attribute | 
|--|--|--|
| Bald | 11719 | 1424
| Bangs | 10985 | 2158
| Black Hair | 11386 | 1715
| Blond Hair| 12584 | 559
| Brown Hair | 8326 | 4822
| Bushy Eyebrows| 6092 | 7119
| Eyeglasses| 10666  | 2477
| Male |2962  | 10181
| Mouth Slight Open| 7610 | 5609
| Mustache| 11536 | 1673
| No Beard | 3746 | 9397
| Pale Skin |6479  | 6664
| Young | 10399 | 2744


## LFW attribute distribution 
The actual images will have the value based on data from Dataset LFW of 5721 individuals, 13143 photos in total, and a text file with an attribute will have the following value: 0 = has no attribute, 1 = has an attribute, The Dataset's owner has also divided the Attribute. We divided the images from the text attribute file into folders using a classifier and discovered that specific images did not fit the attribute. After visually separating the photos, we used the Confusion Matrix to gauge their accuracy. The results are as follows.

| Attribute | TP | TN | FP|FN |
|--|--|--|--|--|
| Bald |1321  |11136 |103| 583
| Bangs | 1139  |10966 |1019 |19
| Black Hair |  1119 | 10981|638|405
| Blond Hair| 515  |12202 |44|382
| Brown Hair | 1915  |8089 |2907| 237
| Bushy Eyebrows|  6857 |5959 | 262| 237
| Eyeglasses| 2070  |10501 |407|165
| Male | 9821 | 2608|360|354
| Mouth Slight Open|  5457 |2608 |76|2250
| Mustache| 1541 |11427 |66|129
| No Beard | 6368 | 3078|29|668
| Pale Skin | 6588 |6435 |76|44
| Young | 2673  |10273 |71|126

## Generate from AttGAN
Using the pre-trained AttGAN model, we can generate a synthetic image and modify its attributes by changing the intensity of the attribute level. The following thirteen attributes can be created using AttGAN: Bald, Bangs, Black Hair, Blond Hair, Brown Hair, Bushy Eyebrows, Eyeglasses, Male, Mouth Slightly Open, Mustache, No Beard, Pale Skin, Young.Generating that image can be performed in a variety of formats, including

[AttGAN-PyTorch](https://github.com/elvisyjlin/AttGAN-PyTorch),

## Requirements
* Python 3
* PyTorch 0.4.0
* TensorboardX
* Keras
* Keras_vggface
* Keras-applications
* Mtcnn
* Sklearn
