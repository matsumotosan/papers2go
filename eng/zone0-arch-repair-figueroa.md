# A computational analysis of different endograft designs for Zone 0 aortic arch repair
Authors: Theodorus M. van Bakel, Christopher J. Arthurs, Joost A. van Herwaarden, Frans L. Moll, Kim A. Eagle, Himanshu J. Patel, Santi Trimarchi, C. Alberto Figueroa

Journal: European Journal of Cardio-Thoracic Surgery

Year: 2018

## Summary
* Endografts for endovascular repair of aortic arch an alternative for patients advised against open surgical repair for various aortic pathologies
  * Endograft in ascending aorta to redirect flow to brachiocephalic trunk (BCT) alone or to left common carotid artery (LCCA) as well

<p align="center">
  <img src="https://qph.fs.quoracdn.net/main-qimg-5a744b4c00f29ca33cfd2a523e33a7dc" />
</p>

  * Effects on postoperative hemodynamics unclear (especially in cervical arteries)
  * Goal: assess and compare various Zone 0 endograft designs with CFD
* Patient-specific CFD model
  * Geometry from patient with saccular aortic arch aneurysm
  * Built preoperative model that matches patient-specific measurements

  <p align="center">
    <img src="https://github.com/matsumotosan/papers2go/blob/master/img/eng/zone0-arch-repair-figueroa/geometries.png" />
  </p>

  * Modified preoperative model to model 4 postoperative geometries for various endograft designs
  * All geometries run with same inflow and outflow BCs
    * Inflow: from echocardiography data
    * Outflow: Windkessel (RCR) model
      * Parameters set to match clinical measurements of patient
    * 6% of cardiac output to each subclavian artery
  * Newtonian, incompressible NS, rigid wall assumption
* Total cervical blood flow (CBF) reduced in all endovascular repair scenarios
  * Double branch (scenarios 1 & 2) performed better than single branch (scenarios 3 & 4)
  * Reduced CBF may be significant for diseased patients
* Platelet activation potential (PLAP) a metric to quantify risk of thrombus formulation (known common complication)
  * Mean PLAP increased for all scenarios (best-1, worst-3)
  * Increase in PLAP is an unavoidable effect of modified morphology
* Overall, double branch scenarios have better postoperative hemodynamic performance compared to single branch scenarios
  * Double branch scenarios more closely resemble aortic morphology
