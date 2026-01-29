# LNQ2023 MICCAI challenge

The LNQ2023 Challenge provided the **first medical benchmark** for evaluating weakly-supervised segmentation techniques for lymph node segmentation on a large clinical trial dataset.

## Challenge goals

1. Establish a benchmark for mediastinal lymph node identification and segmentation
2. Facilitate development of automated methods for whole-body lymph node quantification
3. Segment all lymph nodes **larger than 1 cm in diameter** in the mediastinum

## Evaluation metrics

- **Dice Similarity Coefficient (DSC)** — spatial overlap
- **Average Symmetric Surface Distance (ASSD)** — boundary accuracy

## Results

| Rank | Team | Key Approach |
|------|------|--------------|
| 1st | Skeleton Suns | nnU-Net + Probabilistic Atlas |
| 2nd | — | Pseudo-labeling |
| 3rd | — | TotalSegmentator + nnU-Net |

The winning team achieved median ASSD lower than 3mm. Top three teams obtained median DSC greater than 69%.

## Learn more

- [LNQ2023 Challenge site](https://lnq2023.grand-challenge.org/)
- [MELBA Special Issue](https://www.melba-journal.org/issues/lnq2023.html)
