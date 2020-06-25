# A machine learning approach to investigate the relationship between shape features and numerically predicted risk of ascending aortic aneurysm
Authors: Liang Liang, Minliang Liu, Caitlin Martin, John A. Elefteriades, Wei Sun
Journal: Biomechanics and Modeling in Mechanobiology
Year: 2017

## Summary
* 25 CT scans of ascending aortic aneurysms (AsAA) converted into triangular mesh
  * Minimum-stretch-based mesh-parameterization to parameterize into 2D quad mesh
  * Remeshed to yield same number of nodes/elements for each geometry
  * Generalized Procrustes Analysis (GPA) to align shapes
  * PCA used to construct statistical shape model (SSM)
    * First 3 PCs explained ~80% of variation
    * Generated 729 artificial shapes from first 3 PCs
* 
