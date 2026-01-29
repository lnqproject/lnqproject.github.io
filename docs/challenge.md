# LNQ2023 MICCAI challenge

The LNQ2023 Challenge provided the **first medical benchmark** for evaluating weakly-supervised segmentation techniques for lymph node segmentation on a large clinical trial dataset.

## Challenge goals

1. Establish a benchmark for mediastinal lymph node identification and segmentation
2. Facilitate development of automated methods for whole-body lymph node quantification
3. Segment all lymph nodes **larger than 1 cm in diameter** in the mediastinum

## Challenge design

The challenge provided 383 training CT scans with only **partial lymph node annotations** — not all lymph nodes were labeled in each scan. Teams had to develop methods to learn from this incomplete supervision. Performance was evaluated against fully annotated validation (20 scans) and test (100 scans) sets.

## Evaluation metrics

- **Dice Similarity Coefficient (DSC)** — spatial overlap between predicted and ground truth segmentations
- **Average Symmetric Surface Distance (ASSD)** — boundary accuracy in millimeters

## Results

| Rank | Team | Dice | ASSD (mm) |
|------|------|------|-----------|
| 1st | Skeleton Suns | 71.2% | 2.95 |
| 2nd | IMR | 70.0% | 4.15 |
| 3rd | CompAI | 69.0% | 5.05 |

Top-performing teams boosted their performance by combining weak supervision with smaller fully annotated external datasets.

---

## Winning approaches

### 1st place: Skeleton Suns

**Team:** Sofija Engelson, Jan Ehrhardt, Timo Kepp, Joshua Niemeijer, Heinz Handels (University of Lübeck, DFKI, German Aerospace Center)

**Approach:** Combined nnU-Net with a probabilistic lymph node atlas derived from registered training images. The atlas provided anatomical priors for loss weighting and post-processing, reducing penalties in high-probability regions to handle partial annotations. Key improvements came from oversampling fully annotated data and aggressive augmentation.

**Key result:** Detected 57% of ground truth lymph nodes compared to 27% using CT data alone.

- [Paper: Learning Mediastinal Lymph Node Segmentation with a Probabilistic Lymph Node Atlas](https://melba-journal.org/papers/2024:009.html)
- [GitHub: MICAI-IMI-UzL/LNQ2023](https://github.com/MICAI-IMI-UzL/LNQ2023)

### 3rd place: CompAI

**Team:** Stefan M. Fischer, Johannes Kiechle, Daniel M. Lang, Jan C. Peeken, Julia A. Schnabel (Technical University Munich, Helmholtz Munich, King's College London)

**Approach:** Used nnU-Net with TotalSegmentator pseudo-labeling — leveraging a 104-structure segmentation tool to identify non-lymph-node anatomy as definite background. Combined multiple public datasets and found that training on all visible lymph nodes (not just enlarged ones) significantly improved performance.

- [Paper: Mask the Unknown: Assessing Different Strategies to Handle Weak Annotations](https://melba-journal.org/papers/2024:008.html)
- [GitLab: compai/MediastinalLymphNodeSegmentation](https://gitlab.lrz.de/compai/MediastinalLymphNodeSegmentation)

### 4th place: DBDMP

**Team:** Litingyu Wang, Yijie Qu, Xiangde Luo, Wenjun Liao, Shichuan Zhang, Guotai Wang (UESTC, Shanghai AI Lab, Sichuan Cancer Hospital)

**Approach:** Dual-branch network with self-supervised pre-training (Model Genesis) and dynamic pseudo-label generation. Two decoders produce predictions that are mixed to create soft labels for unannotated nodes, with consensus-aware loss weighting.

**Key result:** Achieved 55% Dice without using external datasets — improvements of 43 percentage points over supervised-only baselines.

- [Paper: Weakly Supervised Lymph Nodes Segmentation Based on Partial Instance Annotations](https://melba-journal.org/papers/2024:017.html)
- [GitHub: WltyBY/LNQ2023_training_code](https://github.com/WltyBY/LNQ2023_training_code)

---

## Publications

**Challenge overview paper:**

Dorent, R., Khajavi, R., Idris, T., et al. (2025). LNQ 2023 challenge: Benchmark of weakly-supervised techniques for mediastinal lymph node quantification. *Machine Learning for Biomedical Imaging (MELBA)*. [https://doi.org/10.59275/j.melba.2025-d482](https://doi.org/10.59275/j.melba.2025-d482)

## Learn more

- [LNQ2023 Challenge site](https://lnq2023.grand-challenge.org/)
- [MELBA Special Issue](https://www.melba-journal.org/issues/lnq2023.html)
