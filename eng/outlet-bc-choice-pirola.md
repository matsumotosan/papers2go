# On the choice of outlet boundary conditions for patient-specific analysis of aortic flow using computational fluid dynamics

Authors: S. Pirola, Z. Cheng, O.A. Jarral, D.P. O'Regan, J.R. Pepper, T. Athanasiou, X.Y. Xu

Journal: Journal of Biomechanics

Year: 2017

## Summary
- CFD great tool for gaining insights into hemodynamics and biomechanics but heavily influenced by choice of BCs
  - Windkessel BCs at outlets have been shown to reproduce clinically accurate results
  - Goal is to compare commonly used BCs
    - Windkessel model
    - Fixed flow division
    - Patient-specific pressure waveform
    - Zero pressure
- Patient-specific geometry used for analysis
  - Aortic root to descending aorta
  - Includes the three supra-aortic vessels (BCA, LCCA, LSA)
  - Clinical measurements of pressure and flow rate
- Simulation parameters
  - Inlet: subject-specific 3D time-varying velocity profiles
  - Various sets of BCs at outlets (table below)

![bc-sets](/img/eng/bc-comb-pirola.png)
  
  - 3-element Windkessel model (3-EWM) parameters calculated using empirical relationships

![wind-params](/img/eng/windkessel-param-pirola.png)

  - Laminar, Newtonian, rigid wall, run to converged cyclic solution
- Axial velocity along cross-sectional plane in descending aorta used to compare results
  - Instantaneous velocity field mid-systlic accleration (T1), peak systole (T2), and mid-systolic deceleration (T3)
  - OBC1 velocity field best matched clinical data
  - OBC1-4 tended to overestimate peak flow rate (except OBC5 which underestimated)
  - OBC1-4 predicted mean flow rate well (OBC5 underestimated)
  - OBC1-4 predicted flow distribution well (OBC5 underestimated flow rate through branches)

![obc-results](/img/eng/obc-results-pirola.png)

- Aortic pressure waveforms computed at inlet
  - OBC1-3 realistic values for healthy subject, OBC4-5 unrealistic values
  - Only OBC1 captured realistic pressure waveform
- TAWSS similar for OBC1-4
  - High TAWSS at model inlet, branch roots, and inner bend of distal aortic arch
- Overall OBC1 showed results with best agreement to in vivo data
  - 3-EWM a good choice for outlet BCs but more complex lumped parameter models (LPM) exist
- 
