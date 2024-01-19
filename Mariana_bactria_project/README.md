# Bactria project

This folder details the analysis of 8 samples from raw sequencing reads to taxonomic analysis.

## Quality control of sequencing roads

The quality of the sequencing reads was visualized using FASTQC(v0.12.1). Since adapter sequences were still present in the reads and there was an expected decline in quality twoards the end of the reads, they proceeded to sequence trimming.

## Read trimming

The sequences were trimmed using FASTP(v0.23.4) which allows for removal of universal as well as other commonly used adapter sequences. The polyG tail at the end of the reads was also trimmed off.

The quality control reports showing read quality before and after trimming can be found here : 


## Taxonomic assignment using Metaphlan

The reads then proceeded to taxonomic assignemnt which was first performed using Metaphlan(v4.0.3) against the Metaphlan marker gene database (v.mpa_vOct22_CHOCOPhlAnSGB_202212).

The metaphlan output files can be found here and metaphlan output files whose classification has been changed from SGB to GTDB format can be found here.

Merged output files are also available for the sgb based output files and the gtdb based output files.

The progression of reads from quality control to taxonomic assignment with metaphlan can be found here.


## Taxonomic assignment using Kraken (Phanta Pipeline)
The reads were also taxonomically classified using Phanta (workflow for rapidly quantifying taxa from short-read human gut metagenomes) that allows for a host of human gut metagenome databases that can found here:

Phanta output files can be accessed here.


