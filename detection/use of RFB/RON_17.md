# Reverse Connection with Objectness Prior Networks for Object Detection

## Motivation

* This method is put forward at the same time with FPN. Thus it's a little like FPN.
* Combine the SSD(low resolution input and faster speed) like method and faster RCNN(high resolution input? and slower speed) like method.
* Combine different layer's information unlike SSD to produce predict. -> Reverse Connection
* Unlike faster rcnn and FPN, for different layer, give different scale bounding boxes.
* inbalanced ratio between object and non-object -> region proposals, which bring translation variance -> objectness prior

## Proposed Methods

Figure 1: Overall architecture of RON
![](/images/RON_1.png)

Figure 2: Reverse Connection
![](/images/RON_2.png)

Figure 3: Objectness prior
![](/images/RON_3.png)
For every grid, there exist 10 boxes, thus We use a 3 * 3 convolutional layers to produce a equally resolution feature map with ten channel, Then we softmax it to decide the location.

Figure 4: Loss function
![](/images/RON_4.png)

## Learning details

Data augmentation:

* Using the original/flipped input image
* Randomed sampling a patch whose edge length is {4/10, 5/10, 6/10, 7/10, 8/10, 9/10}


## Pros and Cons

* with regard of the performance, it's performance on COCO is so low(Compared to FPN?)

## How to improve the methods?

To be added