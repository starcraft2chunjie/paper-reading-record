# R-FCN

## Motivation

Faster RCNN apply a costly per-region subnetwork hundreds of times. Use fully convolutional with all computation shared on the entire image.

Address a dilemma between translation-invariance in image classification and translation-variance in object detection.

ResNet on faster RCNN insert the RoI pooling layer into convolutions, breaking down translation invariance, which sacrifices training and testing efficiency. FCN use position-sensitive score maps that encodes the position information with respect to a relative spatial position.

## Proposed methods

![](/images/RFCN1_1.png)

The 9 score maps encode the cases of {top-left, top-center, top-right, ... , bottom-right}

For position-sensitive RoI pooling operation, we use average pooling(max pooling is applicable as well), vote by average the scores.
 
## Learning details




## Pros and cons



## How to improve this methods?

* the predict of bounding box regression is a little unsatisfactory. (small object?), for every part, predict a individual offset and then synthesize them?

