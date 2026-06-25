# Whole Genome Bisulfite Sequencing (WGBS) Analysis Pipeline

This repository contains a complete Whole Genome Bisulfite Sequencing (WGBS) data analysis pipeline for genome-wide DNA methylation profiling. The workflow includes quality control, adapter trimming, bisulfite alignment, methylation extraction, and downstream analysis to quantify methylation patterns across CpG, CHG, and CHH contexts.


The pipeline was executed on a high-performance computing (HPC) cluster using SLURM job scheduling.

  Workflow Summary: 
  
Raw paired-end FASTQ files --> Trim Galore (adapter trimming + quality control) --> Bismark (genome preparation + alignment) --> Deduplication & BAM filtering --> Methylation extraction (CpG / CHG / CHH) --> BedGraph generation --> BigWig conversion for visualization --> Genome-wide methylation profiling (ViewBS) --> Gene-level methylation analysis (bedtools + R)


Key Steps
1. Quality Control and Adapter Trimming
Trim Galore was used to remove adapter sequences and low-quality bases. Additional base clipping was applied to reduce bisulfite sequencing bias.

2. Genome Preparation and Alignment
The reference genome was prepared for bisulfite conversion using Bismark, followed by alignment of paired-end reads.

3. BAM Processing
Duplicate reads were removed and only high-quality uniquely mapped reads were retained for downstream analysis.

4. Methylation Extraction
Methylation information was extracted in CpG, CHG, and CHH contexts using Bismark methylation extractor.

5. Coverage and Visualization
Methylation data were converted into BedGraph and BigWig formats for visualization in genome browsers.

6. Genome-wide Methylation Analysis
ViewBS was used to analyze global methylation distribution and regional methylation patterns across the genome.

7. Gene-level Methylation Analysis
Methylation data were intersected with gene annotations using bedtools, and gene-level methylation percentages were calculated using R.
