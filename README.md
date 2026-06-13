# **Project 1 — Image Registration and Quality Assessment**

## **Overview**

This project evaluates the reliability of biological image registration after a controlled translational shift. Registration quality is assessed using RMSE, spatial error maps, control point analysis and validation tests.

The central question is not whether registration succeeds, but whether the result can be trusted for downstream spatial analysis.

---

## **Dataset**

Kather Texture 2016 — H\&E-stained colorectal tissue images (Zenodo DOI: 10.5281/zenodo.53169, CC BY 4.0).

One TUMOR patch (150×150 px, TIFF) was used as the test case.

---

## **Methods**

A controlled translational shift of 10 pixels was applied to create a reference scenario with a known ground-truth displacement. Registration was performed using phase cross-correlation (scikit-image).

**Assessment pipeline:**

* RMSE — global error magnitude  
* Error map — spatial distribution of errors  
* Control points — local alignment verification  
* Error characterisation — systematic vs random components  
* Extended validation — three independent tests (null case, alternative shift, noise)

Results were used to determine data suitability for downstream spatial analysis.

---

## **Results**

### **Key Results**

| Metric | Result |
| ----- | ----- |
| RMSE | 20.69 intensity units |
| Mean error — central zone | 0.0 |
| Mean error — right border | 77.57 intensity units |
| Control points | 0.0 deviation at all 5 positions |
| Validation | passed (null case, alternative shift, noise) |

### **Main Finding**

An RMSE of 20.69 (\~8% of the full intensity range) initially suggested substantial registration error. Spatial analysis revealed that the error was confined to the right border zone and was consistent with a systematic border effect introduced by the spatial transformation. The central tissue area showed no measurable error.

This indicates that a single global metric may not capture the spatial structure of errors, and that robust assessment requires a combination of complementary sources of evidence.

### **Visualisations**

| Original Image | Registration Result |
| ----- | ----- |
|  |  |

| Error Map | Control Points |
| ----- | ----- |
|  |  |

---

## **From Geospatial Analysis to Spatial Biology**

This project applies spatial data quality assessment principles from geodesy, photogrammetry and metrology to biological image registration. Despite differences in scale and subject matter, these disciplines face a similar analytical challenge — evaluating the reliability of spatial data.

| Geodesy / Remote Sensing | Spatial Biology |
| ----- | ----- |
| Earth's surface | Tissue section |
| Geographic coordinates | Cell coordinates |
| Object position error | Cell position error |
| How reliable are these spatial data? | How reliable are these spatial data? |

In Project 1, registration quality was therefore assessed not by a single global metric but through a combination of complementary quality checks: RMSE, spatial error analysis, control points and validation.

For a detailed discussion see [FROM\_GEOSPATIAL\_TO\_SPATIAL\_BIOLOGY.md](https://chatgpt.com/c/FROM_GEOSPATIAL_TO_SPATIAL_BIOLOGY.md)

---

## **Limitations and Future Work**

Within the scope of this study, only translational shift was investigated using a single image from the dataset. Rotation, scaling and combined transformations were not evaluated. Noise robustness was tested at one noise level only. Comparison of registration algorithms is considered a separate task.

**Future Work:**

* v1.1 — rotation analysis  
* v1.2 — scaling analysis  
* v1.3 — combined transformations (translation \+ rotation \+ scaling)  
* v2.0 — validation on multiple images and comparison of registration algorithms

---

## **How to Reproduce**

1. Clone the repository.  
2. Install dependencies:  
   `pip install -r requirements.txt`  
3. Open `Project1_Image_Registration.ipynb` in Google Colab or Jupyter Notebook.  
4. Run all cells sequentially.

The input image (`data/tumor_patch.tif`) is included in the repository.

**Requirements**

Python 3.8+

* numpy  
* scikit-image  
* scipy  
* matplotlib

See `requirements.txt`.

