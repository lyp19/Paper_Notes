
# [GVT-BDNet: Convolutional Neural Network with Global Voxel Transformer Operators for Building Damage Assessment](https://note.youdao.com/old-web/#/file/WEBcb78ae837a8210f167c659933c318d1a/pdf/WEB02ca0b89ba9f8f62e89af2e55ed7f7ec/)


_Oct 2021_

#### Overall impression
They propose Global Voxel Transformer Operators (GVTOs): flexible
attention-operators originally proposed for Augmented Microscopy that
can replace up-sampling, down-sampling, and size-preserving convolutions
within either a U-Net or a general CNN architecture without any limitation.
Dissimilar to local operators, like convolutions, GVTOs can aggregate global
information and have input-specific weights during inference time, improving
generalizability performance, as already proved by recent literature.
They applied GVTOs on a state-of-the-art BDA model and named it GVT-BDNet. We trained and evaluated our proposal neural network on the xBD
dataset; the largest and most complete dataset for BDA. They compared GVT-BDNet performance with the baseline architecture (BDNet) and observed that
the former improves damaged buildings segmentation by a factor of 0.11.
Moreover, GVT-BDNet achieves state-of-the-art performance on a 10% split
of the xBD training dataset and on the xBD test dataset with an overall F1-
score of 0.80 and 0.79, respectively.
To evaluate the architecture consistency, they have also tested BDNet’s
and GVT-BDNet’s generalizability performance on another segmentation
task: Tree & Shadow segmentation. Results showed that both models
achieved overall good performances, scoring an F1-score of 0.79 and 0.785,
respectively.
 
#### Key ideas
- Loss Function Benchmark
  - Weighted Cross-Entropy Loss
  - Focal Loss
  - Dice Loss
  - J Regularization Loss
- Global Voxel Transformer Operators
  - Size Preserving GVTO
  - Down-sampling and Up-sampling GVTOs
  - Positioning GVTOs inside BDNet

#### Technical details



#### Notes
