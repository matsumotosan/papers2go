# Estimation of in vivo constitutive parameters of the aortic wall using a machine learning approach
Authors: Minliang Liu, Liang Liang, Wei Sun
Journal: Computational Methods in Applied Mechanics and Engineering
Year: 2019

## Summary
* Estimation of in vivo patient-specific elastic properties of aortic wall from images a difficult inverse problem
  * Currently, nonlinear optimization techniques used to iterate properties until computational model matches model derived from images (extremely computationally intensive)
  * Deep neural networks trained on FE models proposed as alternative to nonlinear optimization schemes
* Aortic wall modeled using HGO: 5 parameters (C_{10},k_1,k_2,κ,θ)
* Dataset generated from FE simulations
  * Material parameters sampled from convex set of experimentally derived material parameter space
    * HGO parameters from 65 biaxial tension experiments
  * SSM (n_samples=25) used to generate geometries (systolic)
  * SSM-generated systolic geometries and sampled material parameters used to find corresponding diastolic geometries (generalized pre-stressing algorithm)
    * Training/validation set: 15,366 input-output pairs
    * Test set: 225 input-output pairs
  * Uniform wall thickness (1.5 mm)
* ML model: encode systolic and diastolic shapes and find nonlinear mapping between shape codes and material parameters
  * Shape encoding: PCA
    * First 12 principal components (~0.1% error) for both systolic and diastolic shapes
  * Nonlinear mapping: maps 24 shape codes to 5 material parameters
    * 3 layer
    * Softplus activation
    * Adamax optimization
    * LOO cross-validation
    * Normalized mean absolute error for loss function
* NN predicted C_{10}, k_1, θ well but more errors on k_2 and κ
* Limitations
  * Thickness cannot be measured due to partial volume effect
  * Branches trimmed off
  * Residual stresses neglected
  * Homogeneous distribution of material properties
