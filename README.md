# LKHAT
## Hybrid Attention Transformer with Re-parameterized Large Kernel Convolution for Image Super-Resolution. <br>(download paper： https://authors.elsevier.com/a/1jONZxnVKF3Xl)
![image](https://github.com/mzccc1999/LKHAT/blob/main/fig/PA.png)

- The network architecture as shown: <br>
  
![image](https://github.com/mzccc1999/LKHAT/blob/main/fig/architecture.png)

- More information can be found at: https://github.com/mzccc1999/LKHAT

## The codes are based on HAT https://github.com/XPixelGroup/HAT/tree/main

## Environment
- [PyTorch >= 1.7](https://pytorch.org/) **(Recommend **NOT** using torch 1.8!!! It would cause abnormal performance.)**
- [BasicSR == 1.3.4.9](https://github.com/XPixelGroup/BasicSR/blob/master/INSTALL.md) 
### Installation
Install Pytorch first. <br>
Then,
```
pip install -r requirements.txt
python setup.py develop
```

## How To Train
- Refer to `./options/train` for the configuration file of the model to train.
- Preparation of training data can refer to [this page](https://github.com/XPixelGroup/BasicSR/blob/master/docs/DatasetPreparation.md).
- The training command is like
```
CUDA_VISIBLE_DEVICES=0,1,2,3,4,5,6,7 python -m torch.distributed.launch --nproc_per_node=8 --master_port=4321 lkhat/train.py -opt options/train/train_LKHAT_SRx2_from_scratch.yml --launcher pytorch
```
## How To Test
```
python lkhat/test.py -opt options/test/LKHAT_SRx4.yml
```
The pretrained weights can be find at (https://pan.baidu.com/s/1StVUmovKDg2WqxyApz3eiA?pwd=W6FK)

# Citation
```
@article{MA2024105162,
title = {Hybrid attention transformer with re-parameterized large kernel convolution for image super-resolution},
journal = {Image and Vision Computing},
volume = {149},
pages = {105162},
year = {2024},
issn = {0262-8856},
doi = {https://doi.org/10.1016/j.imavis.2024.105162},
url = {https://www.sciencedirect.com/science/article/pii/S0262885624002671},
author = {Zhicheng Ma and Zhaoxiang Liu and Kai Wang and Shiguo Lian},
}
```

