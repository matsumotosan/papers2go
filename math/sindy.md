# Discovering governing equations from data by sparse identification of nonlinear dynamical systems
Authors: Steven L. Brunton, Joshua L. Proctor, J. Nathan Kutz
Journal: Proceedings of the National Academic of Sciences of the United States of America
Year: 2016

## Summary
* Discovery of the governing equations for a dynamical system purely from data a long-sought goal in physics
  * Must balance model complexity (fewer terms) and accuracy (overfitting)
* Sparse identification of nonlinear dynamics (SINDy)
  * Solving for dynamical systems of the form
<p align="center">
  <img src="https://github.com/matsumotosan/papers2go/blob/master/img/math/sindy/system.png" />
</p>
  * Key insight/assumption: many systems governed by only a few functions ("sparse in the space of possible functions")
  * Collect data on state x(t) and calculate/collect data on its time derivative
<p align="center">
  <img src="https://github.com/matsumotosan/papers2go/blob/master/img/math/sindy/state.png" />
</p>
  * Construct library of candidate nonlinear functions: can be randomly chosen or chosen based on domain knowledge
    * Constant, polynomial, trigonometric, etc.
<p align="center">
  <img src="https://github.com/matsumotosan/papers2go/blob/master/img/math/sindy/library.png" />
</p>
  * Solve sparse regression problem to determine coefficients for Ξ (LASSO)
    * Sparsity forces only critical terms to be kept
  <p align="center">
    <img src="https://github.com/matsumotosan/papers2go/blob/master/img/math/sindy/sparse_regression.png" />
  </p>
  * If only state X(t) is available, approximate derivative of X(t) but can be noisy
    * Use total variation regularization to denoise derivative
  * Many physical systems lead to very large domains (i.e. fluid flow) -> millions of grid points leads to giant matrices
    * Can find low-rank approximation using dimensionality reduction techniques (proper orthogonal decomposition (POD))
    * Express data with low-rank basis
* Lorenz system
  * SINDy correctly identifies terms in original Lorenz system based only on state X(t) and its time derivative
<p align="center">
  <img src="https://github.com/matsumotosan/papers2go/blob/master/img/math/sindy/sindy_schematic.png" />
</p>
* Vortex shedding behind obstacle (flow past a cylinder)
  * Large state dimension -> reduce dimensionality with POD -> express state in new low-rank bases
  *
