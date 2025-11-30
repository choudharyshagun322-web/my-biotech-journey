# Transcriptomics (RNA-Seq) Tools

RNA-Seq measures the expression level of genes. The goal is often to find **Differentially Expressed Genes (DEGs)**—genes that are significantly more or less active in one condition compared to another (e.g., tumor vs. normal tissue).

| Tool | Purpose | Description |
| :--- | :--- | :--- |
| **HISAT2 / STAR** | Align RNA-Seq Reads | Specialized aligners that are "splice-aware," meaning they can handle the way RNA is processed in eukaryotes. |
| **StringTie / featureCounts** | Quantify Expression | Counts how many reads map to each gene. This generates a table of raw counts. |
| **DESeq2 (in R)** | Differential Expression | A very popular R package that takes raw counts and performs statistical analysis to find DEGs. |
| **EdgeR (in R)** | DEG Analysis | An alternative, also very popular, R package for differential expression analysis. |
| **Enrichr / DAVID** | Pathway Analysis | Once you have a list of DEGs, these tools help you figure out what biological pathways they are involved in (e.g., "cell cycle" or "metabolism"). |
