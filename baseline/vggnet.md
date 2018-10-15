# VggNet

## Motivation
Experiment the depth of network's effect on the performance

## Proposed methods

replace 5 * 5 and 7 * 7 conv layer with stacked 3 * 3 conv layer for :

* less parameter but equal receptive field
* more rectification layers make decision function more discriminative.

1 * 1 conv layer for:

* increase the non-linearity without changing receptive field


## Learning details

batchsize: 256

momentum: 0.9

weight decay: 

dropout: 0.5

learning rate: 10^-2 and decrease by a factor of 10 when the validation set accuracy stop improving.

iterations: 370K iteration(74 epoches)

to be added


## Pros and cons

to be added

## How to improve this method?

to be added