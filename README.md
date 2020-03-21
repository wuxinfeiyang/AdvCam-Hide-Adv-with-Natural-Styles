# AdvCam-Hide-Adv-with-Natural-Styles [Paper](https://arxiv.org/abs/2003.08757)

Code for "Adversarial Camouflage: Hiding Physical-World Attacks with Natural Styles"
<p align='center'>
  <img src='results/1-1.png' width='200'/>
  <img src='results/1-2.png' width='200'/>
  <img src='results/3-1.png' width='200'/>
  <img src='results/3-2.png' width='200'/>
</p>
<p align='center'>
  <img src='results/4-1.png' width='200'/>
  <img src='results/4-2.png' width='200'/>
  <img src='results/5-1.png' width='200'/>
  <img src='results/5-2.png' width='200'/>
</p>
<p align='center'>
  <img src='results/6-1.png' width='200'/>
  <img src='results/6-2.png' width='200'/>
  <img src='results/7-1.png' width='200'/>
  <img src='results/7-2.png' width='200'/>
</p>

## Installation

#### Dependencies
* cuda==9.0.176
* cudnn==7.0.5

We highly recommend using [conda](https://www.anaconda.com/distribution/).
```sh
conda create -n advcam_env python=3.6
source activate advcam_env
```
After activating virtual environment:
```sh
git clone https://github.com/RjDuan/AdvCam-Hide-Adv-with-Natural-Styles
cd AdvCam-Hide-Adv-with-Natural-Styles
pip install --user --requirement requirements.txt
```
Download [VGG19.npy](https://mega.nz/#!xZ8glS6J!MAnE91ND_WyfZ_8mvkuSa2YcA7q-1ehfSm-Q1fxOvvs) under folder /vgg19

**Note: We use tensorflow v1 in the code, incompatible with python>3.6 when we test.**

## Usage
#### Quick Start
Running our given example:
```sh
sh run.sh
```
**Note: we set iteration as 4000 for making sure a successful adversary, but adv with better visual performance can be found in earlier iterations.**

#### Basic Usage
* Path to images
  * Put target image, style image, and their segmentations in folders. We set the name of target/style image and their segmentation are same by default. 
  * Modify run.sh and advcam_main.py if you change the path to images.
  * We define the segmentation in following way, you can change it in utils.py

Segmentation type | RGB value
------------ | -------------
UnAttack | <(128,128,128)
Attack | >(128,128,128)

* Parameters
  * Parameters can be speicified in either run.sh or advcam_main.py.

* Run the follow scipt
```sh
sh run.sh
```
## Usage example

A few motivating examples of how AdvCam can be used. 

#### Adv Images
Three adverarial images generated by AdvCam with natural adversarial perturbation.
![Adv image](https://github.com/RjDuan/AdvCam-Hide-Adv-with-Natural-Styles/blob/master/results/adv_group.png)
#### Physical Test
![Physical test](https://github.com/RjDuan/AdvCam-Hide-Adv-with-Natural-Styles/blob/master/results/AdvCam-gif2.gif)

#### More generation and test details can be found in video [AdvCam](https://www.youtube.com/watch?v=gk3NHY_gpvg)

## Acknowledgments
* We use [Yang's code](https://github.com/LouieYang/deep-photo-styletransfer-tf) for style transfer part.
* We use VGG19 implemented by [Chris](https://github.com/machrisaa/tensorflow-vgg)

## Citation
```
@InProceedings{Duan_2020_CVPR,
author = {Duan, Ranjie and Ma, Xingjun and Wang, Yisen and Bailey, James and Qin, A. K. and Yang, Yun},
title = {Adversarial Camouflage: Hiding Physical-World Attacks with Natural Styles},
booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
month = {June},
year = {2020}
}
```

