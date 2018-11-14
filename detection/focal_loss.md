# Focal Loss for Dense Object Detection

## Motivation

* Detection: 
    * two-stage: classifier-> sparse set of candidate object location
    * one-stage: classifier-> regular,dense sampling object location
    * accuracy difference: extreme foreground-background class imbalance encountered during training of dense detector

* solution: reshape the standard cross entropy loss: down-weights the loss assigned to well-classified examples

* effect: train on a sparse set of hard examples and prevent the vast number of easy negative from overwhelming the detector during training(easy negatives contribute no useful learning signal also overwhelm training)

* experiment: RetinaNet

## Proposed Method

![](/images/focal_loss.png)

For easy classified examples(Pt > 0.7 for example), the contribution to loss is less.

## Implement detail

### RetinaNet Detector

A really simple one stage network which is based on resnet and FPN.

## Pros and Cons

Pros: Quite a few

Cons: ???

## How to improve this method

To be added