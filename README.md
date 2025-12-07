# Calumet Metabarcoding Reference Library
The Calumet Metabarcoding Reference Library is a growing library of commonly used metabarcoding markers for specimen from the Calumet Region of the United States. Answering calls from Kartzinel et al's *Global Availability of Plant DNA Barcodes as Genomic Resources to Support Basic and Policy-Relevant Biodiversity Research* to expand reference libraries - and specifically local libraries - we hope to create easier access to a local reference library for taxa in the Calumet-region of Illinois/Indiana. 

Library is based off the database created by Reddy et al., 2025 *VoronaGasyCodes: A Public Database of MitochondrialBarcodes for Malagasy Birds*

Do you have sequences from Calumet taxa that can be inputted into this library? Let us know! We want to try to keep this database as up to date as possible and include as many local sequences as possible.

## How to Use Library

Library can be used using BLAST+ in a conda environment. Steps to install and use conda can be found [here](https://docs.conda.io/projects/conda/en/latest/index.html). Steps are below:

1. Create conda environment
```
conda create -n calumet_blast
conda activate calumet_blast
```
2. Install BLAST+ onto your System
```
conda install bioconda::blast
```
3. Create Calumet Directory
```
mkdir Calumetreflib
cd Calumetreflib
```
4. Download the fast file for preferred marker
```
wget (insert example url here)
```
5. Create local Calumet database
```
makeblastdb -in Calumetexample.fasta -dbtype nucl -out Calumetreflib
```
6. Perform BLAST+ search. The number of cores, the format of the document, and max number of search selections can be adjusted, for more information visit the [BLAST+ Documentation](https://www.ncbi.nlm.nih.gov/books/NBK279690/).
```
blastn -query RNP_NGS_aves_seq.fasta -db VoronaGasyCodes -outfmt 6 -num_threads 4 -max_target_seqs 5 -out Calumet_test_results.txt
```
