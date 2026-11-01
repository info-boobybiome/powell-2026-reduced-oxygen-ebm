# Powell et al. (2026): Oxygen exposure and expressed breast milk storage

Source data, analysis code and statistical outputs for:

> Powell M, Gurr C, Jones S, O'Driscoll T, Ames R, Durmaz A, Thompson W, Eaton S, Bajaj-Elliott M, Mapstone L. **Oxygen Exposure Influences Microbial, Nutritional and Olfactory Characteristics of Expressed Breast Milk During Storage.** *Frontiers in [journal]*, 2026. DOI: [to be added on publication]

This repository holds the complete data and analyses underlying the figures and results reported in the paper. The study compared expressed breast milk (EBM) stored under reduced-oxygen and aerobic conditions for bacterial viability, total antioxidant capacity, vitamin C, long-chain polyunsaturated fatty acids (LC-PUFAs) and olfactory characteristics.

## Contents

Each analysis is in its own folder with the same layout:

```
<analysis>/
├── <Analysis>.Rmd   # R Markdown analysis script
├── <data>.xlsx      # source data
├── results/         # statistics, descriptives and sensitivity analyses (CSV), plus sessionInfo.txt
└── figures/         # figures as PDF and PNG
```

| Folder | Analysis | Paper figure |
|---|---|---|
| `optimal-growth-curves/` | Growth of breast-milk-associated *Bifidobacterium* strains under reduced-oxygen and aerobic conditions (OD600) | Figure 1 |
| `time-kill-curves/` | Viability of *Bifidobacterium* strains following atmospheric oxygen exposure (CFU/mL) | Figure 2 |
| `probiotic-spike-EBM/` | *Bifidobacterium* viability in stored EBM | Figure 3 |
| `antioxidants/` | Total antioxidant capacity of stored EBM | Figure 4 |
| `vitaminC/` | Vitamin C (ascorbic acid) concentration in stored EBM | Figure 5 |
| `LCPUFA/` | EPA and DHA abundance relative to palmitic acid, baseline and day 7 | Figure 6, Figure S4 |
| `olfactory/` | Olfactory ratings, descriptors and blinded forced-choice assessments | Figure 7, Figure S5 |
| `pathogen-spike-EBM/` | Recovery of opportunistic bacterial contaminants in stored EBM | Figure 8 |
| `citations/` | Citations for the R packages used | - |

## Reproducing the analyses

Analyses were run in R 4.5.1 using R Markdown. Key packages: nlme 3.1-168, lme4 1.1-38, lmerTest 3.1-3, ordinal 2026.7-26 and vegan 2.7-5. Full package versions for each analysis are recorded in its `results/sessionInfo.txt`.

1. Install the required packages:

   ```r
   install.packages(c("readxl", "dplyr", "tidyr", "purrr", "tibble", "glue",
                      "ggplot2", "patchwork", "scales", "ggbeeswarm", "ggtext",
                      "nlme", "lme4", "lmerTest", "ordinal", "vegan",
                      "knitr", "rmarkdown"))
   ```

2. Knit any `.Rmd` from inside its own folder (paths are relative), for example:

   ```r
   setwd("vitaminC")
   rmarkdown::render("VitaminC.Rmd")
   ```

   Outputs are written to that folder's `results/` and `figures/`.

## Data and ethics

The study was approved by the University College London Research Ethics Committee (Project ID: 2154), and informed consent was obtained from all participants. All donor and assessor data are de-identified and referred to by codes only. No identifiable participant information is included.

Detailed strain-level information on bacterial isolates from the BoobyBiome strain collection is not disclosed, for the reasons given in the paper's proprietary materials statement.

## Funding

Funded by BoobyBiome Ltd., with additional funding from Innovate UK (grant number 10058431).

## Citation

If you use this data or code, please cite the paper above.

## Licence

Code is released under the MIT Licence. Data are released under CC BY 4.0. [Confirm before publishing]

## Contact

Corresponding author: Lydia Mapstone (lydia@boobybiome.com), BoobyBiome Ltd., London, United Kingdom.
