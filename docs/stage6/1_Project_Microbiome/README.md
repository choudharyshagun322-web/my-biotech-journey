# Project 1: Microbiome Analysis using QIIME2 + LEfSe

🎯 **Goal:** Go from raw sequencing data to identifying key bacterial species that differ between two groups. This is a classic and highly valuable project.

---

### Project Steps:

1.  **Find Data:**
    *   Go to the NCBI Sequence Read Archive (SRA).
    *   Search for a 16S rRNA sequencing dataset that compares two simple groups (e.g., "healthy" vs. "disease" or two different environments).
    *   Download the raw FASTQ files for a small number of samples (e.g., 5 vs 5).

2.  **Run the QIIME2 Pipeline:**
    *   Follow the standard QIIME2 "Moving Pictures" tutorial workflow.
    *   Import your downloaded data.
    *   Run DADA2 for denoising and feature table creation.
    *   Assign taxonomy to your features.
    *   Generate alpha and beta diversity metrics and plots.

3.  **Identify Biomarkers with LEfSe:**
    *   Export your feature table and taxonomy from QIIME2.
    *   Format the data for LEfSe.
    *   Use a Galaxy server or a command-line installation of LEfSe to identify which microbes are significantly enriched in each of your groups.

4.  **Report:**
    *   Create a simple report (e.g., in a Jupyter Notebook or R Markdown file) that visualizes the diversity plots and the final LEfSe results.
    *   Explain your findings in simple terms.
