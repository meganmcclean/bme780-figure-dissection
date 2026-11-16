# Getting the Chu et al. (1998) Yeast Sporulation Dataset

The example notebooks use a synthetic dataset with the same structure as the real data. To run the analysis on the actual data, replace the data-generation block with one of the options below.

---

## Option 1: Download from SGD (Saccharomyces Genome Database)

The original data supplement is archived at SGD:

1. Go to [yeastgenome.org](https://www.yeastgenome.org)
2. Search for "Chu 1998 sporulation"
3. Download `Supplemental_Table_1` (the full timecourse expression matrix)

The file is tab-delimited. Load it with:

```python
import pandas as pd
df = pd.read_csv('chu1998_sporulation.txt', sep='\t', index_col=0)
X = df.values  # shape: (n_genes, 7)
```

---

## Option 2: Use the Alter et al. (2000) Processed Version

Alter, Brown & Botstein (2000) [doi:10.1073/pnas.97.18.10101](https://doi.org/10.1073/pnas.97.18.10101) provide a processed version of the same dataset as a supplement. This version has already been log-transformed and filtered.

---

## Option 3: Use a Built-In Teaching Dataset

The R/Bioconductor package `yeastCC` contains the Cho et al. 1998 cell-cycle data (a related dataset). The Spellman et al. 1998 dataset is another option available in multiple R packages.

For Python, the `scikit-learn` datasets module does not include this dataset, but it can be loaded via the `gseapy` package:

```python
# pip install gseapy
import gseapy
# See gseapy documentation for GEO dataset access
```

---

## Timepoints

The 7 sporulation timepoints in Chu et al. 1998 are:
**0, 0.5, 2, 5, 7, 11, 14 hours**

The cluster labels (Early I, Early II, Early Middle, Middle, Middle Late, Late, Metabolic) are from Table 1 of Chu et al. 1998.
