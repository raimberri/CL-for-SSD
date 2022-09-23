# AML Project

Name:Yicheng Ma	NetID:ym1956

Continual learning of Single Shot Multibox Detector on Large dataset

## Environments

1. Ubuntu 20.04
2. Python 3.8.5
3. Pytorch 1.6.0
4. RTX 2080Ti with 11GB RAM
5. CUDA 10.1 and cuDNN 8.0

## Results

| Tasks                    | VOC 2007(mAP) | VOC 2012(mAP) |
| ------------------------ | ------------- | ------------- |
| Joint Learning           | 0.739         | 0.701         |
| Standard Loss(Only 2007) | 0.712         | -             |
| Standard Loss(Only 2012) | 0.699         | 0.670         |
| Feature Map Loss         | 0.713         | 0.675         |

Experiment results of MS COCO datasets are not valid due to unfixed bugs of training(localization loss didn't converge well and results in abnormal bounding boxes and mAPs).

Results of standard SSD model on COCO 2017:

|      | VGG based | Resnet-50 based |
| ---- | --------- | --------------- |
| mAP  | 1.8%      | 0.5%            |

## Instructions

1. Download Pascal VOC2007 [trainval dataset](http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtrainval_06-Nov-2007.tar) and [test dataset](http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar). Merge the two folders 'VOC2007'.
2. Download Pascal VOC2012 [trainval dataset](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/VOCtrainval_11-May-2012.tar).
3. Put the folders 'VOC2007' and 'VOC2012' into the 'data' folder.
4. Download pretrained models from [here](https://drive.google.com/drive/folders/12tJamsGLKmtIyfr9xuNs9vPuu-SkYtif?usp=sharing) and put them into 'Checkpoint' folder.
5. Use eval_FML_*.ipynb to evaluate pretrained FML model.
6. Use train_FML_*.ipynb to train a new model.

## Reference

Code modified from:  
https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Object-Detection  
https://github.com/amdegroot/ssd.pytorch  
https://github.com/lufficc/SSD

