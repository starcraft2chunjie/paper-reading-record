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

The essence of this method is to add some flexibility into the layer. for deeper layer, it can choose the weight of preceding layer output and current layer output because when network is deeper, we can't tell which layer contribute less, so we add preceding layer output to learn to flexibly choose the layer.

## How to improve this method?

* give more flexibility. Not for one preceding layer but n preceding layers having a shortcut connection to it. 
* To be added











