# [S2Looking: A Satellite Side-Looking Dataset for Building Change Detection](https://arxiv.org/pdf/2107.09244.pdf)

_Sep 2021_

#### Overall impression
This paper therefore introduces S2Looking, a building change detection dataset that contains large-scale sidelooking satellite images captured at various off-nadir angles. The dataset consists of 5000 bitemporal image pairs of rural areas and more than 65,920 annotated instances of changes throughout the world. 
It expands upon existing datasets by providing: 1) larger viewing angles; 2) large illumination variances; and 3) the added complexity of rural images. 
The dataset is available at [](https://github.com/S2Looking/)

#### Key ideas
- View transformer: both neural feature transformation and geometric projection. HDMapNet does not predict depth of monocular cameras at all but use MLP to map pixels from perspective to BEV.
- Image encoder
	- perspective view image encoder: EfficientNet-B0 pretrained.
	- neural view transformer (MLP): from $H_{pv} \times W_{pv}$ perspective view feature map spatial dimension to $H_c \times W_c$ top down spatial dimension. The MLP is shared channel-wisely and does not change the feature dimension (Note: should be num of feature channels?). --> This proves to be better than [Lift Splat Shoot](lift_splat_shoot.md).
	- the camera features are then transformed to **ego vehicle frame** with using extrinsics. Final feature is the **average** of $N_m$ camera features.
- Point cloud encoder
	- point-pillars. 
	- concatenated with camera feature if lidar branch exists
- BEV decoder
	- semantic segmentation
	- instance embedding: push-pull loss
	- lane direction: 2-hot encoding. For background the label is 0.
- Postprocessing
	- vectorization: DBSCAN + NMS, then connecting with direction.
- Evaluation
	- Semantics metrics
		- Eulerian metric: pixel value, IoU.
		- Lagrangian metric: structured outputs, Chamfer distance
	- Instance metrics
		- TP, F1 score

![](https://cdn-images-1.medium.com/max/1600/1*HwMxIxdiuEewezEp7VSk_Q.png)

- vectorized output of 3 classes (lane line, boundary and pedestrian crossing)
- optional early fusion of camera and lidar

#### Technical details
- ICP and NDT (normal distribution transform) to do lidar alignment/registration.
- Drawbacks of IPM: IPM assumes a flat ground plane. Predictions in each view are not easily combined to a holistic view.
- MLP is better than IPM (assuming ground plane) and depth prediction (Lift Splat Shoot).
- Different categories are not equally recognizable in one modality. Road boundary are more recognizable with lidar than lane lines. 

#### Notes
- The BEV decoder can be useful for top-down view image recognition. This solves two issues
	- Clustering of close-by objects, even if they intersect or are close by
