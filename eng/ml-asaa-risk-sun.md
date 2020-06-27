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
* FE modeling on all generated shapes (ABAQUS)
  * Steps
    1. Backward displacement method to estimate unpressurized geometry
    2. Inflation of unpressurized geometry to rupture
  * Simulation conditions
    * Uniform thickness (2mm) as thickness cannot be measured from CT scans
    * Uniform pressure applied to inner surface
  * Constitutive model
    * HGO model (fixed for all simulations)
    * Parameters fit from AsAA tissue sample
    * Failure defined using equivalent strain from tissue damage theory
    * Pressure risk ratio (PRR) defined as P_{sys}/P_f where P_f is the failure pressure for each model
* ML-based estimation of rupture risk
  * Features extracted: maximum diameter, average centerline curvature, average surface curvature, SSM parameters
  * Support vector machine (SVM) used to classify low risk and high risk
    * Observational features not good at predicting risk levels
    * SSM parameters ~95% accuracy on test set
  * Support vector regression (SVR) used to regress PRR
    * Combining intuitive shape features with SSM parameters lowered error dramatically
* Limitations
  * Constitutive parameters set and equal for all
  * Mean thickness
    * Addition of statistical thickness model (STM) to capture variation in thickness
  * Effect of branches unclear
    * Suggested remeshing branching vessel surfaces and stitching all mesh segments together
  * Residual stresses neglected
