
# [CondLaneNet: a Top-to-down Lane Detection Framework Based on Conditional Convolution](https://arxiv.org/abs/2105.05003)

_May 2021_

#### Overall impression
In this work,they propose CondLaneNet,a novel top-to-down lane detection framework that detects the lane instances first and then dynamically predicts the line shape for each instance.AInming to solve lane instance-level discrimination problem,they introduce a conditional lane detection strategy based on convolution and row-wise formulation.Further,they deisign the Recurrent Instance Module(RIM) to overcome the problem of detecting lane lines with complex topologies.

#### Key ideas
- Instance Detection
  They detect the lane instacne by detecting the proposal point located at the start point of the line.

<!-- \ell _{point} = \frac{-1}{N_{p}}\sum_{xy}\left\{\begin{matrix} (1 - \hat{P_{xy}})^{\alpha} log(\hat{P_{xy}})\quad \hat{P_{xy}}=1  \\
(1 -{P_{xy}})^{\beta}(\hat{P_{xy}})^{\alpha }log(1 - \hat{P_{xy}}) \quad otherwise
\end{matrix}\right. -->
![image](https://user-images.githubusercontent.com/83415336/147550668-44477980-b2c5-4941-a87d-7c9d287d572c.png)


  - 
#### Technical details



#### Notes
