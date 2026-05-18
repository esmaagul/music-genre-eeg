# 🧠🎵 EEG Music Genre Classification

> Analyzing the neurological effects of music genres on the human brain using EEG signals and machine learning.

## Overview

This project uses the **MUSIN-G dataset** (OpenNeuro ds003774) to classify music genres based on EEG brain signals. The pipeline covers raw signal processing, artifact removal, frequency feature extraction, and ML classification.

---

## Setup

### 1. Open in Codespace
**Code → Codespaces → Create codespace on main**

### 2. Download Data
```bash
mkdir -p data/raw outputs

for sub in 001 002 003 004 005; do
  aws s3 sync s3://openneuro.org/ds003774/sub-$sub/ data/raw/sub-$sub/ \
    --no-sign-request \
    --exclude "*" \
    --include "*.set" --include "*.fdt" --include "*.tsv" --include "*.json"
done
```

### 3. Run Notebooks in Order
```
01_data_exploration → 02_preprocessing → 03_feature_extraction → 04_classification
```

---