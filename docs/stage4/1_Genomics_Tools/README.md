# Essential Genomics Tools (WGS/WES Pipeline)

This is the mandatory toolkit for any research role involving Whole Genome Sequencing (WGS) or Whole Exome Sequencing (WES). The workflow involves taking raw sequencing data and processing it to identify genetic variants like SNPs and indels.

| Tool | Used For | Description |
| :--- | :--- | :--- |
| **FastQC** | Quality Control | Inspects your raw FASTQ files to check for quality issues before you start analysis. |
| **Trimmomatic / Cutadapt** | Read Trimming | Removes low-quality bases and adapter sequences from your reads. Garbage in, garbage out! |
| **BWA / Bowtie2** | Read Alignment | Aligns your cleaned reads to a reference genome, creating a SAM/BAM file. |
| **SAMtools** | BAM/SAM Handling | A multi-tool for sorting, indexing, and viewing alignment files. Absolutely essential. |
| **GATK** | Variant Calling | The industry standard for identifying differences (variants) between your sample and the reference genome. |
| **IGV** | Genome Visualization | A desktop tool for visually inspecting your alignment (BAM) and variant (VCF) files. It lets you *see* the data. |
