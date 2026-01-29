# Dataset: Mediastinal-Lymph-Node-SEG

## Collection summary

| Attribute | Value |
|-----------|-------|
| **Full name** | Mediastinal Lymph Node Quantification (LNQ): Segmentation of Heterogeneous CT Data |
| **Patients** | 513 |
| **Series** | 1,026 (513 CT + 513 SEG) |
| **Images** | 66,870 |
| **Total size** | 35.27 GB |
| **License** | CC BY 4.0 |
| **Last updated** | August 2024 |

## Access

- [Mediastinal Lymph Node SEG on IDC](https://portal.imaging.datacommons.cancer.gov/explore/filters/?collection_id=mediastinal_lymph_node_seg) — Cloud-based access with BigQuery
- [CT Lymph Nodes on IDC](https://portal.imaging.datacommons.cancer.gov/explore/filters/?collection_id=ct_lymph_nodes) — Related NIH lymph node dataset

## Data contents

| Modality | Series | Total Size | Avg per Series |
|----------|--------|------------|----------------|
| CT | 513 | 34.96 GB | 68 MB |
| SEG | 513 | 314 MB | 0.6 MB |

**Annotation types:**

- **Fully annotated:** 120 cases (all mediastinal lymph nodes segmented)
- **Partially annotated:** 393 cases (one or more lymph nodes segmented)

## Data source

The dataset originates from the **Tumor Imaging Metrics Core (TIMC)**, a multi-institutional imaging core lab comprising:

- Massachusetts General Hospital
- Dana Farber Cancer Institute
- Brigham and Women's Hospital

TIMC provides multimodality imaging measurements to evaluate treatment response in patients enrolled in oncology clinical trials, having processed data from **over 1,400 clinical trials** conducted between 2007–2020.

## Patient population

All scans were captured at baseline timepoints during clinical trials. The top six primary cancers (60% of patients):

- Breast cancer
- Chronic lymphocytic leukemia (CLL)
- Non-small cell lung cancer
- Hodgkin's lymphoma
- Small cell lung cancer
- Renal cell cancer

Additional cancer types (40% of patients): thyroid, adenocarcinoma, endometrial adenocarcinoma, melanoma, head and neck, non-Hodgkin's lymphoma, prostate, mesothelioma, esophageal, ovarian, colon.

---

## Methodology

### Annotation process

1. **Clinical trial localization**
   Initial lymph node localization performed during clinical trial reads by TIMC staff. Each case reviewed by US board-certified radiologists.

2. **3D Slicer segmentation**
   CT scans and bidimensional measurements loaded into 3D Slicer (v4.11). Segment Editor module used for manual delineation at native CT resolution.

3. **Freehand boundary drawing**
   Draw tool used to create freehand boundaries on axial cross-sections while referencing sagittal and coronal planes. Large vessels, artifacts, and non-nodal components excluded from lesion boundaries.

4. **De-identification & quality review**
   Data fully de-identified per MGB IRB approval (2020P000211 and 2020P003754). All header data manually reviewed; image series checked for quality and de-identification integrity.

### Annotator qualifications

All annotators were trained radiologists or radiology domain experts with **over 10 years of experience**.
