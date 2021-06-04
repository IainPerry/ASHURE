A modified version of the ashure ASHURE analysis tool, designed to identify Sars-covid-19 variants in Wate-water. The use of nanopore sequencing with its rapid sequencing make it ideal for testing waste-water for the presence of covid-variants (and other pathogens). However the sequencing accuracy remains a significant issue when calling variants. Here we leverage RCA to error correct nanopore sequencing error for ARTIC amplicons using a modified version of ASHURE developed by https://github.com/BBaloglu/ASHURE.
Please read and cite ASHURE for more information.
-------------
1: Alignment against ARTIC covid amplicons to identify and label fragments
2: Running per sequence, cut out repeats (in memory) and generate consesus, outputting to a csv
3: Filter out consensus with fewer than 10 repeats and outside minimum expected amplicon length
4: Clustering?
4: Convert to Fasta and map to covid genome with STAR

## Installation 
singularity build --remote ncov-ashure.sif Singularity.recipe

## Getting started
```
singularity run ncov-ashure.sif -i data.fastq
```
Example usage from the clustering module
```bash
./ashure.py clst -h                                           # prints help
./ashure.py clst -i input.csv -o clusters.csv -r              # runs clustering
./ashure.py clst -i input.csv -o clusters.csv -c config.json  # updates config.json with custom parameters
```


## Citing ASHURE

Read our paper here: https://besjournals.onlinelibrary.wiley.com/doi/epdf/10.1111/2041-210X.13561

If you use ASHURE in your work, please cite:

    Baloğlu, B., Chen, Z., Elbrecht, V., Braukmann, T., MacDonald, S. and Steinke, D. (2021). A workflow for accurate metabarcoding using nanopore MinION sequencing. Methods Ecol Evol. 2021;12:794– 804. https://doi.org/10.1111/2041-210X.13561
    
    Baloğlu, B. & Chen, Z. (2021). ASHURE. Version 1.0.0. Zenodo. DOI: 10.5281/zenodo.4450611
