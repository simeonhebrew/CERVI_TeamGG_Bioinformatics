# Virome Analysis using Phanta

This repository contains the analysis descritpion of Control, IgAD and CVID virome samples whose raw sequences can be found [here](https://www.dropbox.com/scl/fo/24yneco04qzdfrzua01qj/h?rlkey=gwg5zutg2hfqchb4goy94liim&dl=0).


## Quality control of sequencing reads

The quality of the sequencing reads was visualized using `FASTQC (v0.12.1)`. Since adapter sequences were still present in the reads and there was an expected decline in quality twoards the end of the reads, they proceeded to sequence trimming.


## Sequence read trimming

The sequences were trimmed using `FASTP(v0.23.4)` which allows for removal of universal as well as other commonly used adapter sequences. The polyG tail at the end of the reads was also trimmed off.

The quality control reports showing read quality before and after trimming can be found [here](https://github.com/simeonhebrew/CERVI_TeamGG_Bioinformatics/tree/main/Virome_Phanta_Results/trimmed_reads_quality_reports).

## Taxonomic assignment using Phanta

The reads were also taxonomically classified using `Phanta(v1.1.0)` (workflow for rapidly quantifying taxa from short-read human gut metagenomes) using a group of human gut metagenome databases. Phanta implements Kraken2 as a taxonomic classifer based on k-mer 
alignment.

The phanta output folders are organized for [Control](https://github.com/simeonhebrew/CERVI_TeamGG_Bioinformatics/tree/main/Virome_Phanta_Results/final_merged_outputs_Control), [IgAD](https://github.com/simeonhebrew/CERVI_TeamGG_Bioinformatics/tree/main/Virome_Phanta_Results/final_merged_outputs_IgAD) and [CVID](https://github.com/simeonhebrew/CERVI_TeamGG_Bioinformatics/tree/main/Virome_Phanta_Results/final_merged_outputs_CVID) samples in which the files are organized as follows;

*counts.txt* - provides the number of read (pairs) assigned to each taxon

*counts_family.txt* - filtered *counts.txt* at family level

*counts_genus.txt* - filtered *counts.txt* at family level

*host_control.txt* - predicted host genera and corresponding viral abundance

*lifestyle0.8.txt* - predicted viral lifestyle statistics		

*relative_read_abundance.txt* - same as *counts.txt* but normalized out of the total number of reads in each sample that were ultimately assigned to any taxon during abundance estimation

*relative_taxonomic_abundance.txt* - similar to *relative_read_abundance.txt* but abundances are corrected for genome length. In addition, only species (and not higher taxonomic levels) are included in this report.

*total_reads.tsv* - tracking of assigned and unassigned reads

The control, CVID and IgAD viral and host count files have been merged under the prefix 'PAD' and can be found here [here](https://github.com/simeonhebrew/CERVI_TeamGG_Bioinformatics/tree/main/Virome_Phanta_Results/PAD_count_outputs).

The overall progression of reads from quality control to taxonomic assignment can be found [here](https://github.com/simeonhebrew/CERVI_TeamGG_Bioinformatics/blob/main/Virome_Phanta_Results/Virome_Reads_Phanta_Analysis.xlsx).


