# Lymph Node Quantification (LNQ) Project

**Advancing automated analysis of lymph nodes in imaging**

---

## Overview

The Lymph Node Quantification (LNQ) Project is working to develop new computational techniques to measure and analyze lymph nodes throughout the body. Our work addresses a critical gap in current cancer imaging and treatment: accurate lymph node size estimation is essential for cancer staging, therapeutic management, and monitoring treatment response over a patient's treatment course.

Current clinical practice relies on simple length measurements on just one or a few nodes, typically from a single imaging slice. New 3D segmentation and analysis methods promise better sensitivity that can, for example, show whether a patient's medical therapy is effective.

In addition to its own work, the LNQ Project is actively promoting awareness of the importance of lymph node analysis in the medical imaging community. In particular, we have made CT scans and segmentation patient data available to the public and conducted a "Grand Challenge" competition between different research groups to analyze that data.

## What are lymph nodes?

Lymph nodes are small organs throughout the body that filter fluids and help fight infection. When cancer spreads, it often travels through the lymphatic system, causing nearby lymph nodes to enlarge. Measuring these nodes on CT scans is essential for staging cancer, planning treatment, and monitoring response to therapy—but current clinical practice relies on simple 2D measurements of just a few nodes, missing critical information about total disease burden.

### Clinical impact

Lymph node status is one of the most powerful predictors of cancer outcomes. For lung cancer, the five-year survival rate drops from 63% when the disease is localized to 35% when it has spread to regional lymph nodes. These measurements directly influence whether patients receive surgery, chemotherapy, radiation, or combinations thereof. With over 2 million Americans diagnosed with cancer each year, even modest improvements in measurement accuracy could affect treatment decisions for millions of patients.

### Why automated quantification matters

Automated 3D segmentation of all enlarged lymph nodes promises to detect changes to disease earlier, reduce variability between different radiologists, and provide a more complete picture of disease status. As these tools become validated and widely deployed, they could help standardize care quality across hospitals and enable earlier detection of treatment response or progression—when clinical intervention can still make a difference.

### Why lymph node quantification is difficult

**Hard to see**
On CT scans, lymph nodes often look very similar to surrounding tissue, with blurry edges that make them difficult to spot—even for experienced radiologists.

**Irregular shapes**
Diseased lymph nodes don't follow a predictable form. They can merge together into larger masses, and range from 5mm (normal) to several centimeters (diseased).

**Limited training data**
Teaching computers to find lymph nodes requires manually labeled examples, but creating these pixel-by-pixel annotations is extremely time-consuming—limiting the data available for machine learning.

**Incomplete measurements**
The chest alone may contain ten or more lymph nodes, often with several enlarged beyond 1cm. Yet current clinical practice measures only a few, missing the bigger picture.
