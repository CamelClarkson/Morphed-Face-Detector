[![DOI](https://zenodo.org/badge/412588846.svg)](https://zenodo.org/badge/latestdoi/412588846)


# Morphed Face Detector
A MobileNetV2 based morphed face detector trained on a variety of morphs. The morph detector works on images of resolution 1024 x 1024 and is trained against StyleGAN, OpenCV, and FaceMorpher morphs on the FERET and Face Research Lab London (FRLL) databases.


## Setup
Make sure tensorflow v2 is installed, e.g., using Anaconda
```
conda install tensorflow-gpu <cudatoolkit=<CUDA_VERSION>
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

## Citations
If you use this software please cite our work and the databases the model was trained against
```bibtex
@unknown{unknown,
author = {Sarkar, Eklavya and Korshunov, Pavel and Colbois, Laurent and Marcel, Sébastien},
year = {2020},
month = {12},
pages = {},
title = {Vulnerability Analysis of Face Morphing Attacks from Landmarks and Generative Adversarial Networks}
}
```
