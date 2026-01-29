# Lymph Node Quantification (LNQ) Project

**Advancing automated analysis of lymph nodes in imaging**

---

## Overview

The Lymph Node Quantification (LNQ) project is addressing a critical gap in cancer imaging: the need for accurate, automated 3D segmentation and analysis of lymph nodes throughout the body. Accurate lymph node size estimation is essential for cancer staging, therapeutic management, and monitoring treatment response over a patient's treatment course.

Current clinical practice relies on simple length measurements on just one or a few nodes, typically from a single imaging slice. More advanced methods such as 3D segmentation and analysis promise better sensitivity that can, for example, show whether therapy is effective. 

## Introduction: what are lymph nodes?

Lymph nodes are small organs throughout the body that filter fluids and help fight infection. When cancer spreads, it often travels through the lymphatic system, causing nearby lymph nodes to enlarge. Measuring these nodes on CT scans is essential for staging cancer, planning treatment, and monitoring response to therapy—but current clinical practice relies on simple 2D measurements of just a few nodes, missing critical information about total disease burden.

### Clinical impact

Lymph node status is one of the most powerful predictors of cancer outcomes. For lung cancer, the five-year survival rate drops from 63% when the disease is localized to 35% when it has spread to regional lymph nodes. These measurements directly influence whether patients receive surgery, chemotherapy, radiation, or combinations thereof. With over 2 million Americans diagnosed with cancer each year, even modest improvements in measurement accuracy could affect treatment decisions for millions of patients.

### Why automated quantification matters

Automated 3D segmentation of all enlarged lymph nodes promises to detect changes to disease earlier, reduce variability between different radiologists, and provide a more complete picture of disease status. As these tools become validated and widely deployed, they could help standardize care quality across hospitals and enable earlier detection of treatment response or progression—when clinical intervention can still make a difference.

| Quick Facts | |
|-------------|---|
| **Challenge** | MICCAI 2023 |
| **Dataset** | 513 patients, 35.3 GB |
| **License** | CC BY 4.0 |
| **DOI** | [10.7937/QVAZ-JA09](https://doi.org/10.7937/QVAZ-JA09) |

---

## The problem

### Why lymph node quantification is difficult

**Low contrast boundaries**
Lymph nodes often share intensity profiles with surrounding soft tissue and have ill-defined borders, making them difficult to identify even for experienced radiologists.

**Complex morphology**
Nodes can become confluent, forming larger matted structures with no characteristic shape. Their size varies from 5mm (normal) to several centimeters (diseased).

**Annotation scarcity**
Full pixel-level ground truth annotations are extremely time-consuming to create, limiting the training data available for machine learning approaches.

**Limited current practice**
The mediastinum may contain ten or more lymph nodes, often with three or more enlarged greater than 1cm—yet standard measurements capture only a fraction of this information.

---

## LNQ2023 MICCAI challenge

The LNQ2023 Challenge provided the **first medical benchmark** for evaluating weakly-supervised segmentation techniques for lymph node segmentation on a large clinical trial dataset.

### Challenge goals

1. Establish a benchmark for mediastinal lymph node identification and segmentation
2. Facilitate development of automated methods for whole-body lymph node quantification
3. Segment all lymph nodes **larger than 1 cm in diameter** in the mediastinum

### Evaluation metrics

- **Dice Similarity Coefficient (DSC)** — spatial overlap
- **Average Symmetric Surface Distance (ASSD)** — boundary accuracy

### Results

| Rank | Team | Key Approach |
|------|------|--------------|
| 1st | Skeleton Suns | nnU-Net + Probabilistic Atlas |
| 2nd | — | Pseudo-labeling |
| 3rd | — | TotalSegmentator + nnU-Net |

The winning team achieved median ASSD lower than 3mm. Top three teams obtained median DSC greater than 69%.

---

## Dataset: Mediastinal-Lymph-Node-SEG

### Collection summary

| Attribute | Value |
|-----------|-------|
| **Full Name** | Mediastinal Lymph Node Quantification (LNQ): Segmentation of Heterogeneous CT Data |
| **Patients** | 513 |
| **Series** | 1,026 (513 CT + 513 SEG) |
| **Images** | 66,870 |
| **Total Size** | 35.27 GB |
| **License** | CC BY 4.0 |
| **Last Updated** | August 2024 |

### Data contents

| Modality | Series | Total Size | Avg per Series |
|----------|--------|------------|----------------|
| CT | 513 | 34.96 GB | 68 MB |
| SEG | 513 | 314 MB | 0.6 MB |

**Annotation types:**

- **Fully Annotated:** 120 cases (all mediastinal lymph nodes segmented)
- **Partially Annotated:** 393 cases (one or more lymph nodes segmented)

### Data source

The dataset originates from the **Tumor Imaging Metrics Core (TIMC)**, a multi-institutional imaging core lab comprising:

- Massachusetts General Hospital
- Dana Farber Cancer Institute
- Brigham and Women's Hospital

TIMC provides multimodality imaging measurements to evaluate treatment response in patients enrolled in oncology clinical trials, having processed data from **over 1,400 clinical trials** conducted between 2007–2020.

### Patient population

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

---

## Resources & access

### Data portals

| Resource | Description | Link |
|----------|-------------|------|
| **TCIA** | Primary collection with NBIA Data Retriever | [cancerimagingarchive.net](https://www.cancerimagingarchive.net/collection/mediastinal-lymph-node-seg/) |
| **IDC Portal** | Cloud-based access with BigQuery | [portal.imaging.datacommons.cancer.gov](https://portal.imaging.datacommons.cancer.gov/explore/filters/?collection_id=mediastinal_lymph_node_seg) |
| **Zenodo** | Archived challenge data | [doi.org/10.5281/zenodo.7844666](https://doi.org/10.5281/zenodo.7844666) |

### Challenge & publications

| Resource | Link |
|----------|------|
| LNQ2023 Challenge | [lnq2023.grand-challenge.org](https://lnq2023.grand-challenge.org/) |
| MELBA Special Issue | [melba-journal.org/issues/lnq2023](https://www.melba-journal.org/issues/lnq2023.html) |
| TIMC | [tumormetrics.org](https://www.tumormetrics.org/) |

---

## Citation

If you use this dataset in your research, please cite:

> Idris, T., Somarouthu, S., Jacene, H., LaCasce, A., Ziegler, E., Pieper, S., Khajavi, R., Dorent, R., Pujol, S., Kikinis, R., & Harris, G. (2024). *Mediastinal Lymph Node Quantification (LNQ): Segmentation of Heterogeneous CT Data* (Version 1) [Data set]. The Cancer Imaging Archive. https://doi.org/10.7937/QVAZ-JA09

---

## Funding

This project was funded by Brigham and Women's Hospital through NIH grant **5R01CA235589** "Lymph Node Quantification System for Multisite Clinical Trials."

---

*Data hosted by [The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/) and [NCI Imaging Data Commons](https://portal.imaging.datacommons.cancer.gov/)*
