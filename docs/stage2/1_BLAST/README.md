# BLAST — Your First Tool

💡 **Purpose:** Sequence similarity search. Given a sequence, BLAST finds regions of similarity against a massive database of known sequences.

🧪 **Use Cases:**
*   **Identifying unknown sequences:** You have a piece of DNA, what is it?
*   **Checking for contamination:** Are there non-target sequences in your sample?
*   **Finding homologous genes:** Finding genes with shared ancestry in other species.

---

### Getting Started

The easiest way to start is with the web interface.

📚 **Web Resource:** [https://blast.ncbi.nlm.nih.gov](https://blast.ncbi.nlm.nih.gov)

---

### Core Concepts to Learn

*   **BLASTn:** Nucleotide BLAST (DNA vs DNA database).
*   **BLASTp:** Protein BLAST (Protein vs Protein database).
*   **E-value (Expect value):** The number of hits you would expect to see by chance. **Lower is better.** An E-value of 0.001 is much more significant than an E-value of 10.
*   **Identity %:** The percentage of characters that are identical between your query and the result.
*   **Query Coverage:** The percentage of your query sequence that aligns with the result.
