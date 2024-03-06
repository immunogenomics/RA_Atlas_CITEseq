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

*** Data Description ***

```
Bcell_reference.rds
Bcell_uwot_model
Bulk_7samples_AMP-ids.rds
CTAP_donor_mapping.xlsx
NK_reference.rds
NK_uwot_model
T_reference.rds
T_uwot_model
all_cells_reference.rds
all_cells_uwot_model
endothelial_reference.rds
endothelial_uwot_model
fibroblast_reference.rds
fibroblast_uwot_model
fine_cluster_all_314011cells_82samples.rds
myeloid_reference.rds
myeloid_uwot_model
qc_mRNA_314011cells_log_normalized_matrix.rds
qc_protein_CLR_normalized_filtered_matrix.rds
raw_mRNA_count_matrix.rds
raw_protein_count_matrix.rds
```


## Contact
Please email Fan Zhang (fanzhanglab@gmail.com) and Helena Jonsson (a.helena.jonsson@gmail.com) for any questions.
