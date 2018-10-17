# Feature pyramid networks

## Motivation

To be more robust to scale-variance and to be more accurate. To leverage the pyramidal shape of a ConvNet's feature hierachy while creating a feature pyramid that has strong semantics at all scales.

Inspired by out-network feature pyramid called featurized image pyramids. We use in-network feature pyramids without sacrificing representational power, speed, and memory.

## Proposd Methods

Instead of Featurized image pyramids(different scale image, weakness: Inference time increase and used only test time given memory)

Instead of SSD(Use only layers that high up in the net-work, without higher-resolution maps of the feature hierachy)

To achieve this, creating a architecture that combines low-resolution, semantically strong features with high-resolution, semantically weak features via a top-down pathway and lateral connections.

![](/images/FPN1_1.png)

![](/images/FPN1_2.png)

![](/images/FPN1_5.png)

For lateral connections, the 1 * 1 conv for reducing the dimension and use the nearest neighbour upsampling for simplicity.

## Learning details

images: resized with shorter sides has 800 pixels.

optimization: synchronized SGD

mini-batch: 2 images per GPU and 256 anchors per image.

weight decay: 0.0001

momentum: 0.9

learning rate: 0.02 for the first 30k mini-batches and 0.002 for the next 10k

## Pros and cons

Cons: For top-down pyramid only, the location of features are not precise because it's downsampled and upsampled seveal times. More precise locations of features can be passed from the finer levels of the bottom-up maps via the lateral connections. 

## Usage

### Used for RPN

For FPN, we design the design(3 * 3 conv and two sibling 1 * 1 conv) to each level on feature pyramid. So we assign anchors of a single scale to each level. We define the anchors to have different areas of pixels on {P2, P3, P4, P5, P6} respectively. For each level, we use multiple aspec ratios at each level.

![](/images/FPN1_3.png)

### Used for Fast R-CNN

Assign RoIs of different scales to the pyramid levels.
![](/images/FPN1_4.png)

## What we can do to improve this method?

* to design better connection modules?(concatenate?)

* top-down pyramid be carefully designed？(upsample, add a resnet to top-down pyramid?)




