# [BDANet: Multiscale Convolutional Neural Network with Cross-directional Attention for Building Damage Assessment from Satellite Images](https://arxiv.org/pdf/2105.07364.pdf)

_May 2021_

#### Overall impression
 In this paper, they propose a novel two-stage convolutional neural network for Building Damage Assessment, called BDANet. In the
first stage, a U-Net is used to extract the locations of buildings.
Then the network weights from the first stage are shared in
the second stage for building damage assessment. In the second
stage, a two-branch multi-scale U-Net is employed as backbone,
where pre- and post-disaster images are fed into the network
separately. A cross-directional attention module is proposed to
explore the correlations between pre- and post-disaster images.
Moreover, CutMix data augmentation is exploited to tackle the
challenge of difficult classes. The proposed method achieves stateof-the-art performance on a large-scale dataset – xBD. The code
is available at https://github.com/ShaneShen/BDANet-BuildingDamage-Assessment
 
#### Key ideas

#### Technical details



#### Notes
