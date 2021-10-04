[![DOI](https://zenodo.org/badge/412588846.svg)](https://zenodo.org/badge/latestdoi/412588846)


# Morphed Face Detector
A MobileNetV2 based morphed face detector trained against a large database of [morphs](https://arxiv.org/abs/2012.05344). The morph detector works on images of resolution 1024 x 1024 and is trained against StyleGAN, OpenCV, and FaceMorpher morphs on the FERET and Face Research Lab London (FRLL) databases.


## Setup
Make sure tensorflow v2 is installed, e.g., using Anaconda
```
conda install tensorflow-gpu cudatoolkit=<CUDA_VERSION>
```
Install the repo in the desired project directory.

## Usage
The morph detector takes in 1024x1024x3 input images and ouputs a one-hot vector for the two classes with unscaled logits.
The output follows the following convention for lablelling the two classes
```
[0, 1] denotes a morph
[1, 0] denotes a bona fide face
```
To load the model the following commands need to be used
```python
import tensorflow as tf

model = tf.keras.model.load_model('morph_detector')
```
To get the label predictions use the following code
```python
predicted_labels = model.pred(input_images)
```
 ## Citation
 If you use this software, please cite this work
 ```bibtex
 @software{Blasingame_MorphedFaceDetector_2021,
author = {Blasingame, Zander and Liu, Chen},
doi = {10.5281/zenodo.5544552},
month = {10},
title = {{Morphed-Face-Detector}},
url = {https://github.com/zblasingame/Morphed-Face-Detector},
version = {1.0.0},
year = {2021}
}```

