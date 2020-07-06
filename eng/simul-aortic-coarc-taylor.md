# Computational Simulations for Aortic Coarctation: Representative Results From a Sampling of Patients
Authors: John F. LaDisa, Jr., C. Alberto Figueroa, Irene E. Vignon-Clementel, Hyun Jin Kim, Nan Xiao, Laura M. Ellwein, Frandics P. Chan, Jeffrey A. Feinstein, Charles A. Taylor

Journal: Journal of Biomechanical Engineering

Year: 2011

## Summary
* Coarctation of aorta (CoA): narrowing of aorta
* Long-term results of CoA treatment show various complications despite successful initial treatment
  * Initially hypothesized that altered ascending aorta hemodynamics lead to reductions in aortic capacitance and elevated pulse BP
  * Goal: better understand pre- and post-operative hemodynamics of CoA that lead to complications
* Simulation setup
  * Models built from segmentations of MRI data
  * Inflow BCs: parabolic flow profile assigned based on PC-MRI waveforms
    * For normal patient: resting CO determined from body surface area and a normal cardiac index of 3.5 L/min/m^2
      * Flow to branches estimated using relationship between branch diameter and ascending aorta flow
  * Outflow BCs: three-element Windkessel model
    * Resting conditions: total arterial capacitance estimated from inflow and BP measurements with total resistance ratio of 6%
    * Terminal resistance calculated from mean BP and PC-MRI flow measurements and distributed among remaining parameters with pulse pressure method
  * Wall deformation: coupled-momentum method formulation
    * Membrane model for vessel wall (uniform thickness: 0.15 cm)
* 
