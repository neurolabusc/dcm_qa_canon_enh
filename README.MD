## About

dcm_qa_canon_enh is an enhanced DICOM dataset to validate conversion of Canon (né Toshiba) diffusion tensor imaging. This repository is for enhanced (4D) images, for classic DICOM see [dcm_qa_canon](https://github.com/neurolabusc/dcm_qa_canon). Specifically, to ensure that the DICOM gradient vector direction are transformed to match the FSL standard. Note that different vendors use [different conventions](https://www.na-mic.org/wiki/NAMIC_Wiki:DTI:DICOM_for_DWI_and_DTI) to report gradient directions. The goal is to convert these to [FSL's bvec format](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FDT/FAQ#What_conventions_do_the_bvecs_use.3F) which is in [image space](http://justinblaber.org/brief-introduction-to-dwmri/).

The images were acquired on a Canon Galan 3T by Clément Debacker at Le Groupe Hospitalier Universitaire Paris. [Xiangrui Li](https://ccbbi.osu.edu/people/li.2327), Chris Rorden and [Arnaud Le Troter](https://crmbm.univ-amu.fr/contact/le-troter-arnaud/) helped decipher the usage of DICOM tags by Canon. 

These images report gradient orientation with respect to the scanner bore (like Siemens, Philips and UIH), rather than the image space (like GE). For example, a volume might report:

```
 (0018,9087) FD 1500                                     #   8, 1 DiffusionBValue
 (0018,9089) FD 0.29387456178665161\-0.95365142822265625\-0.064700603485107422 #  24, 3 DiffusionGradientOrientation
```

The provided dataset adjusts the acquisition orientation (axial, coronal, sagittal) and the image angulation. The rationale is to identify whether an image-space or world-space frame of reference is used, and to ensure that these are accurately transformed to FSL's image space format. A [dedicated document](https://www.nitrc.org/plugins/mwiki/index.php/dcm2nii:MainPage#Diffusion_Tensor_Imaging) describes this procedure.


## Series

* 9000-DTI-PA-ortho
  * Description: Axial scan acquired orthogonal to the scanner bore, Posterior to Anterior (PA) phase encoding.

* 10000-DTI-AP-ortho
  * Description: Axial scan acquired orthogonal to the scanner bore, Anterior to Posterior (AP) phase encoding.

* 11000-DTI-PA-SAG_20d
  * Description: Sagittal scan acquired with 20-degree angulation applied, PA phase encoding.

* 12000-DTI-PA-AX_20d : Axial scan acquired with 20-degree angulation applied, PA phase encoding.

* 13000-DTI-PA-COR_20d
  * Description: Sagittal scan acquired with 20-degree angulation applied.

* 14000-DTI-PA-ALL_20d
  * Description: Axial scan acquired with all axes rotated 20 degrees, Posterior to Anterior (PA) phase encoding.

* 32000-DTI-PA-ortho-HT
  * Description: Axial scan acquired orthogonal to the scanner bore, Posterior to Anterior (PA) phase encoding. Head turned of about 45 degrees on the right.

* 33000-DTI-PA-ortho-HT-VT
  * Description: Axial scan acquired, Posterior to Anterior (PA) phase encoding. Head turned of about 45 degrees on the right. In-plane angulation applied to match head rotation.

* 37000-SAG-DTI-PA-ortho
  * Description: Sagittal scan acquired orthogonal to scanner bore, PA phase encoding.

* 39000-SAG-DTI-PA-ALL_20d
  * Description: Sagittal scan acquired with all axes rotated 20 degrees, Posterior to Anterior (PA) phase encoding.

