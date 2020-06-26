# DeepSDF: Learning Continuous Signed Distance Functions for Shape Representation
Authors: Jeong Joon Park, Peter, Florence, Julian Straub, Richard Newcombe, Steven Lovegrove
Journal: arXiv
Year: 2019

## Summary
* Current state of 3D shape representation learning
  * Representations
    * Point-based: point clouds, does not describe topology, not suitable for producing watertight surfaces
    * Mesh-based: fixed mesh topology leads to limitations, parameterization techniques limited by mesh quality, spherical parameterization good for closed meshes but limited to topological spheres
    * Voxel-based: limited to low-resolutions as compute grows cubically
  * Representation learning techniques
    * GANs: can produce very realistic results but training known to be unstable
    * Auto-encoders: can learn shape features well with regularization, VAEs
    * Auto-decoders (new idea): optimize latent vectors for each sample, eliminates need to train encoder
* Modeling SDFs with neural networks
  * Signed distance function (SDF)
    * Function that defines a point's distance to the closest point on a surface
    * Distance is negative if inside and positive if outside of the surface
    * Surface implicitly defined as zero level-set of SDF
  * DNN can be trained to learn an SDF for a given shape
* Learning latent space of shapes
  * Training DNN to learn SDF for one shape not useful
  * Instead, train DNN to output SDF at a point given the shape codes for a specific shape

<p align="center">
  <img src="https://github.com/matsumotosan/papers2go/blob/master/img/ml/deepsdf/deepsdf.png" />
</p>

  * Encoder part of auto-encoder not used after training (motivates auto-decoder architecture)
  * Auto-decoder details
    * Goal: learn latent code for each shape and train decoder network
    * Training: randomly initialize latent code for each shape in training set and update latent vectors and decoder weights through backpropagation
    * Inference: fix decoder weights and estimate optimal latent vector for shapes

<p align="center">
  <img src="https://github.com/matsumotosan/papers2go/blob/master/img/ml/deepsdf/autodecoder.png" />
</p>
