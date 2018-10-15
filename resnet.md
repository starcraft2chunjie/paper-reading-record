# ResNet

## Motivation

To handle the problem of degradation(deeper network has worse performance) which is proved not to be caused by overfitting, vanishing/exploding gradients(BN used)

## Proposed methods

y = F(x) + x(identity mapping) or y = F(x) + Wx(projection shortcuts) which added Shortcut Connections

![](/images/paper1_1.png)
![](/images/paper1_2.png)
## Learning details

### Implementation

preprocessing: image shorted side random sampled in [256, 480], 224 * 224 crop is random sampled from an image or horizontal flip, per-pixel mean subtracted. standard color augmentation. 

BN used. 

batchsize: 256

learning rate: 0.1->divided by 10 when error plateaus

iteration: 60 * 10 ^4 iteration

weight decay: 0.0001

momentum: 0.9

no dropout

testing: 10-crop testing, fully-convolutional form, average the score at multiple scales(shorter size in {224, 256, 384, 480, 640})

### Experiment

1.28 million training images 50k validation images for evaluation and 100k test images

### Usage
#### Object detection baseline
* No hidden fc layers.Use "NoC"("Networks on Conv feature maps")
* Box refinement.("object detection via multi-region")
* Global context. ("global Spatial Pyramid Pooling")
* Multi-scale testing

## Pros and cons

To be added

## How to improve this method?

* Dense net
* To be added










