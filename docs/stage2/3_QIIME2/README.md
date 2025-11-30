# QIIME 2 — The Standard for Microbiome Analysis

💡 **Purpose:** Analyze microbial community sequencing data (e.g., from 16S/18S/ITS rRNA gene sequencing). It takes you from raw sequence files to meaningful biological insights about what microbes are in your samples and how they differ.

It is heavily used in premier research institutes like **NICPR, ICMR-NIV, ICMR-IGIB,** and most academic microbiome labs.

---

### Core Workflow to Learn

1.  **Importing Data:** Getting your raw FASTQ files into the QIIME 2 format.
2.  **Denoising (with DADA2):** A high-resolution method to filter out sequencing errors and identify unique sequences (called Amplicon Sequence Variants or ASVs).
3.  **Taxonomic Assignment:** Matching your ASVs against a reference database to give them names (e.g., *Escherichia coli*).
4.  **Diversity Analysis:**
    *   **Alpha Diversity:** How diverse is a single sample?
    *   **Beta Diversity:** How different are microbial communities between samples?
5.  **Visualization:** Creating plots like PCoA (Principal Coordinates Analysis) to visualize community differences and phylogenetic trees to see evolutionary relationships.

---

### Getting Started

Your experience with Docker and Shell is a huge plus here, as QIIME2 can be tricky to install directly.

📚 **Official Tutorials:** [https://docs.qiime2.org](https://docs.qiime2.org)

The official tutorials are the best place to start. They provide sample data and walk you through the entire standard workflow.
