# Project 2: BLAST + Biopython Automation

🎯 **Goal:** Showcase your scripting skills by creating a tool that automates a common bioinformatics task.

---

### Project Steps:

1.  **Create an Input File:**
    *   Create a multi-FASTA file containing several DNA or protein sequences. These can be sequences you get from NCBI or just example sequences.

2.  **Write a Biopython Script (`blast_automation.py`):**
    *   The script should take the multi-FASTA file as input.
    *   For each sequence in the file, it should:
        *   Use Biopython's `Bio.Blast.NCBIWWW` module to run an online BLAST search (e.g., `blastn` for DNA, `blastp` for protein).
        *   Parse the XML output from the BLAST search.
        *   Extract the top hit (the one with the best E-value).
        *   From that top hit, extract key information: the organism name, the percent identity, the query coverage, and the E-value.

3.  **Generate an Output File:**
    *   The script should write the extracted information into a clean, comma-separated values (`.csv`) file.
    *   The CSV should have clear headers like `Query_ID`, `Top_Hit_Organism`, `Percent_Identity`, `Query_Coverage`, `E-Value`.

4.  **Put it on GitHub:**
    *   Create a new repository on GitHub.
    *   Add your Python script and an example input file.
    *   Write a `README.md` explaining what the script does and how to run it. This demonstrates good documentation practice.
