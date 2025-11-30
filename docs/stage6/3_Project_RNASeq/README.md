# Project 3: RNA-Seq Pipeline (FASTQ → DEG → Pathway Analysis)

🎯 **Goal:** Perform a complete differential gene expression analysis, a cornerstone of modern cancer research.

---

### Project Steps:

1.  **Find Data:**
    *   Go to the Gene Expression Omnibus (GEO) database.
    *   Find an RNA-Seq dataset that compares two conditions (e.g., a tumor type vs. adjacent normal tissue). Look for a study with a small number of samples to start (e.g., 3 vs 3).
    *   Use the SRA toolkit (`fastq-dump`) to download the raw FASTQ files.

2.  **Run the Alignment and Counting Pipeline:**
    *   Perform quality control with **FastQC**.
    *   Use **HISAT2** or **STAR** to align the reads to the appropriate reference genome (human, mouse, etc.).
    *   Use **featureCounts** or **StringTie** to count how many reads map to each gene, creating a count matrix.

3.  **Perform Differential Expression Analysis in R:**
    *   Load the count matrix into R.
    *   Use the **DESeq2** package to perform the statistical analysis.
    *   Generate a list of differentially expressed genes (DEGs) based on a significance threshold (e.g., p-adjusted value < 0.05).
    *   Create a **Volcano Plot** to visualize the results, highlighting the most significant up-regulated and down-regulated genes.

4.  **Perform Pathway Analysis:**
    *   Take your list of significant DEGs.
    *   Use an online tool like **Enrichr** or **DAVID** to see which biological pathways are over-represented in your gene list.

5.  **Report:**
    *   Document your entire workflow, including the commands used and the R code.
    *   Display your volcano plot and the results from the pathway analysis.
    *   This is an advanced project that is highly relevant to cancer research at NICPR.
