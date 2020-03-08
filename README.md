# Gradients as Features for Deep Representation Learning

![alt text](https://github.com/fmu2/gradfeat20/blob/master/paper/overview.png "Method overview")

## This code repository is under construction.

## Overview
This repository contains code for reproducing the results in [Gradients as Features for Deep Representation Learning](https://openreview.net/pdf?id=BkeoaeHKDS) published as a conference paper at ICLR 2020. The code has been tested in an conda environment with Python 3 and PyTorch >= 1.3.

## Quick Start
* Download the base networks [here](http://pages.cs.wisc.edu/~fmu/gradfeat20/pretrained). We currently support BiGAN/ALI encoder pre-trained on CIFAR-10/-100 or SVHN as the base network. In the download link, "ali" stands for ALI trained on Jenson-Shannon divergence, and "wali" stands for ALI trained on Wasserstein distance. See (and star :) ) our [repository](https://github.com/fmu2/Wasserstein-BiGAN) on Wasserstein BiGAN.

   File names with a trailing zero correspond to randomly initialized networks (e.g., fnet0.pt, std_hnet0.pt, etc.).

   File names with a trailing one correspond to networks pre-trained from generative modeling (e.g., fnet1.pt, std_hnet1.pt, etc.).

   File names with the prefix "std" correspond to networks under standard parametrization.
   
   File names with the prefix "ntk" correspond to networks under NTK parametrization.

* Update the loading and saving paths in the configuration files.
* Sample commands (CIFAR-10)

- Activation baseline
```shell
python ./src/benchmark.py -c ./configs/cifar10/ali/actv.config
```
- Full model (i.e., the proposed linear model)
```shell
python ./src/benchmark.py -c ./configs/cifar10/ali/linear_conv3.config
```
- Gradient baseline
```shell
python ./src/benchmark.py -c ./configs/cifar10/ali/grad_conv3.config
```
- Network fine-tuning
```shell
python ./src/benchmark.py -c ./configs/cifar10/ali/finetune_conv3.config
```

## Contact
[Fangzhou Mu](http://pages.cs.wisc.edu/~fmu/) (fmu2@wisc.edu)

## Bibtex
```
@inproceedings{mu2020gradfeat,
  title={Gradients as Features for Deep Representation Learning},
  author={Mu, Fangzhou and Liang, Yingyu and Li, Yin},
  booktitle={International Conference on Learning Representations (ICLR)},
  year={2020}
}
```
