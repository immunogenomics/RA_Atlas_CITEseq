# RA_Atlas_CITEseq

[![DOI](https://zenodo.org/badge/367384023.svg)](https://zenodo.org/badge/latestdoi/367384023)
![](https://komarev.com/ghpvc/?username=immunogenomics&style=flat-square&color=blueviolet)

## Overview
This repo provides the data, code, and website for our work on "Cellular deconstruction of inflamed synovium defines diverse inflammatory phenotypes in rheumatoid arthritis". The data is generated through a collaborative effort with NIH funded [AMP RA/SLE (Accelerating Medicines Partnership Rheumatoid Arthritis and Systemic Lupus Erythematosus)](https://www.niams.nih.gov/grants-funding/funded-research/accelerating-medicines/RA-SLE).


```
- RA Synovial Single-cell Multimodal (transcriptomics and Proteomics) Cell Atlas
- Inflammatory tissue stratification: RA Synovial Cell Type Abundance Phenotypes (CTAPs)
- Associations of certain CTAPs with disease-relevant cytokines, histology, serology metrics
- Reveal significant associations between RA causal genes and cell type-specific synovial CTAPs
- Infer inflammatory phenotypes from clinical trial bulk RNA-seq of RA synovial tissue
- Functional cell-cell interaction and immune mediator assays
- Microscopy analysis for different synovial phenotypes 
```

<img src="https://github.com/immunogenomics/RA_Atlas_CITEseq/blob/master/figure/overview.png" width="800" align="center">



## Citation
Our paper can be cited: Zhang*, Jonsson*, Nathan*, Wei*, Millard*, *et al*, ***Nature***, 2023, https://www.nature.com/articles/s41586-023-06708-y



## Website
Feel free to check out our [Website](https://immunogenomics.io/ampra2/) regarding the single-cell data and results.


## Source code
Source code for reproducing the results are available at our [Github repo](https://github.com/immunogenomics/RA_Atlas_CITEseq).


## Data availability
CITE-seq single-cell expression matrices and sequencing and bulk expression matrices are available on Synapse (https://doi.org/10.7303/syn52297840). 

Associated genotype and clinical data are available through the Arthritis and Autoimmune and Related Diseases Knowledge Portal (ARK Portal, https://arkportal.synapse.org/Explore/Datasets/DetailsPage?id=syn52297840).

#### Data Description: ####

- Each cell type-specific reference is provided based on one cell type-focused analysis. 

```
Bcell_reference.rds
Bcell_uwot_model
NK_reference.rds
NK_uwot_model
T_reference.rds
T_uwot_model
endothelial_reference.rds
endothelial_uwot_model
fibroblast_reference.rds
fibroblast_uwot_model
myeloid_reference.rds
myeloid_uwot_model
```

Every reference data has the same format. Taking one cell type reference as an example, you will see the saved datafrmaes as follows.
```
ref <- readRDS("myeloid_reference_2023-03-12.rds")
str(ref)

 $ meta_data     :'data.frame':	76181 obs. of  7 variables:
  ..$ cell          : chr [1:76181] "BRI-399_AAACCCAGTAGGAGGG" "BRI-399_AAACGCTGTTCAAGTC" "BRI-399_AAAGGATTCTGTACAG" "BRI-399_AAAGGTAAGCTGGCTC" ...
  ..$ sample        : chr [1:76181] "BRI-399" "BRI-399" "BRI-399" "BRI-399" ...
  ..$ cluster_number: chr [1:76181] "M-10" "M-10" "M-0" "M-7" ...
  ..$ cluster_name  : chr [1:76181] "M-10: DC2" "M-10: DC2" "M-0: MERTK+ SELENOP+ LYVE1+" "M-7: IL1B+ FCN1+ HBEGF+" ...
  ..$ nUMI          : num [1:76181] 33644 17084 4999 16721 11235 ...
  ..$ nGene         : int [1:76181] 5515 3806 1770 3767 3101 4788 3460 4028 3463 3152 ...
  ..$ percent_mito  : num [1:76181] 0.0847 0.0446 0.1658 0.1576 0.0129 ...
 $ vargenes      : tibble [3,547 × 3] (S3: tbl_df/tbl/data.frame)
  ..$ symbol: chr [1:3547] "CXCL13" "CCL17" "CHI3L1" "SPP1" ...
  ..$ mean  : Named num [1:3547] 0.0256 0.0208 0.0429 1.0576 0.2033 ...
  .. ..- attr(*, "names")= chr [1:3547] "CXCL13" "CCL17" "CHI3L1" "SPP1" ...
  ..$ stddev: Named num [1:3547] 0.227 0.226 0.192 1.682 0.452 ...
  .. ..- attr(*, "names")= chr [1:3547] "CXCL13" "CCL17" "CHI3L1" "SPP1" ...
 $ loadings      : num [1:3547, 1:20] -0.00166 -0.00647 0.00709 0.00111 0.04714 ...
 $ R             : num [1:100, 1:76181] 2.21e-14 1.81e-06 4.35e-08 3.66e-08 1.70e-14 ...
 $ Z_orig        : num [1:20, 1:76181] -7.567 0.538 -8.644 -5.862 -2.298 ...
 $ Z_corr        : num [1:20, 1:76181] -7.559 -1.46 -5.743 -3.853 0.223 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : chr [1:20] "harmony_1" "harmony_2" "harmony_3" "harmony_4" ...
  .. ..$ : chr [1:76181] "4" "28" "38" "47" ...
 $ centroids     : num [1:20, 1:100] 0.92797 0.29046 -0.05318 -0.00418 -0.00714 ...
 $ cache         :List of 2
  ..$ : num [1:100, 1] 768 865 845 756 775 ...
  ..$ : num [1:100, 1:20] 7880 -11077 -6132 -1873 6180 ...
 $ umap          :List of 1
  ..$ embedding: num [1:76181, 1:2] -5.02 -5.62 1.78 -4.26 -4.35 ...
  .. ..- attr(*, "scaled:center")= num [1:2] 0.19 0.343
  .. ..- attr(*, "dimnames")=List of 2
  .. .. ..$ : NULL
  .. .. ..$ : chr [1:2] "UMAP1" "UMAP2"
 $ save_uwot_path: chr "./myeloid_uwot_model_2021-04-29"
 ```

As you can see above, the `cluster_number` and `cluster_name` are given under `ref$meta_data`. Further, some key outpus are explained as follows:

``` 
# vargenes: variable genes, means, and standard deviations used for scaling
# loadings: gene loadings for projection into pre-Harmony PC space
# R: Soft cluster assignments
# Z_orig: Pre-Harmony PC embedding
# Z_corr: Harmonized PC embedding
# centroids: locations of final Harmony soft cluster centroids
# cache: pre-calculated reference-dependent portions of the mixture model
# umap: UMAP coordinates
# save_uwot_path: path to saved uwot model (for query UMAP projection into reference UMAP coordinates)
```

- CTAP assignment to donor ID:
```
CTAP_donor_mapping.xlsx
```

- Reference for all cell type integrative analysis:
```
all_cells_reference.rds
all_cells_uwot_model
```

- Cluster annotations for fine-grained cell states:
```
`fine_cluster_all_314011cells_82samples.rds`

'data.frame':	314011 obs. of  5 variables:
 $ sample        : chr  "BRI-399" "BRI-399" "BRI-399" "BRI-399" ...
 $ cell          : chr  "BRI-399_AAACGAACAGTCTGGC" "BRI-399_AAAGGATGTCTCAAGT" "BRI-399_AAAGTGACATCGAACT" "BRI-399_AAAGTGAGTGCACAAG" ...
 $ cluster_number: chr  "B-2" "B-1" "B-2" "B-1" ...
 $ cluster_name  : Factor w/ 77 levels "B-0: CD24+CD27+CD11b+ switched memory",..: 2 4 2 4 1 4 3 3 2 8 ...
 $ cell_type     : chr  "B cell" "B cell" "B cell" "B cell" ...
```

- Raw and processed matrices:
```
*raw_mRNA_count_matrix.rds*: Raw mRNA count
*raw_protein_count_matrix.rds*: Raw protein count
*qc_mRNA_314011cells_log_normalized_matrix.rds*: QCed mRNA normalized data matrix
*qc_protein_CLR_normalized_filtered_matrix.rds*: QCed protein normalized data matrix

```


## Contact
Please email Fan Zhang (fanzhanglab@gmail.com) and Helena Jonsson (a.helena.jonsson@gmail.com) for any questions.
