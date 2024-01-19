# Bactria project

This folder details the analysis of 8 samples from raw sequencing reads to taxonomic analysis.
The paired-end raw sequencing reads are located [here](https://www.dropbox.com/home/Dossier%20de%20l'%C3%A9quipe%20Team%20GG/Sequencing_data/2023/230424_NovaSeq_run2_MS_IgA_Virome/2023_NovaSeq_Bacteria/Marianne_Bactria_data).

## Quality control of sequencing roads

The quality of the sequencing reads was visualized using `FASTQC (v0.12.1)`. Since adapter sequences were still present in the reads and there was an expected decline in quality twoards the end of the reads, they proceeded to sequence trimming.

## Read trimming

The sequences were trimmed using `FASTP(v0.23.4)` which allows for removal of universal as well as other commonly used adapter sequences. The polyG tail at the end of the reads was also trimmed off.

The quality control reports showing read quality before and after trimming can be found [here](https://github.com/simeonhebrew/U1135_Bioinformatics/tree/main/Mariana_bactria_project/Mariana_bactria_QC_files) 


## Taxonomic assignment using Metaphlan

The reads then proceeded to taxonomic assignemnt which was first performed using `Metaphlan(v4.0.3)` against the Metaphlan marker gene database `(mpa_vOct22_CHOCOPhlAnSGB_202212)`.

The metaphlan output files can be found [here](https://github.com/simeonhebrew/U1135_Bioinformatics/tree/main/Mariana_bactria_project/Metaphlan_output_files) and metaphlan output files whose classification has been changed from SGB to GTDB format can be found [here](https://github.com/simeonhebrew/U1135_Bioinformatics/tree/main/Mariana_bactria_project/Metaphlan_output_files_gtdb).

Merged output files are also available for the sgb-based [output](https://github.com/simeonhebrew/U1135_Bioinformatics/blob/main/Mariana_bactria_project/merged_output_files/merged_bacteria_metaphlan.tsv) files and the gtdb-based [output](https://github.com/simeonhebrew/U1135_Bioinformatics/blob/main/Mariana_bactria_project/merged_output_files/merged_bacteria_metaphlan_gtdb.tsv) files.

The progression of reads from quality control to taxonomic assignment with metaphlan can be found [here](https://github.com/simeonhebrew/U1135_Bioinformatics/blob/main/Mariana_bactria_project/Bactria_reads_track.xlsx).


## Taxonomic assignment using Kraken (Phanta Pipeline)
The reads were also taxonomically classified using `Phanta(v1.1.0)` (workflow for rapidly quantifying taxa from short-read human gut metagenomes) using a group of human gut metagenome [databases](https://github.com/bhattlab/phanta/blob/main/databases.md). Phanta implements Kraken2 as a taxonomic classifer based on k-mer alignment.

Phanta output files can be accessed [here](https://github.com/simeonhebrew/U1135_Bioinformatics/tree/main/Mariana_bactria_project/phanta_output_mariana_bactria).

The progression of reads from quality control to taxonomic assignment with phanta is located [here](https://github.com/simeonhebrew/U1135_Bioinformatics/blob/main/Mariana_bactria_project/phanta_output_mariana_bactria/final_merged_outputs/total_reads.tsv).


## General microbiome analysis
Diversity and abundance analysis was then performed using `phyloseq (v.1.44.0)` and `microeco v(1.3.0)` based on `R version 4.2.3`.

