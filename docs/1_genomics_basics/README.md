# 1. Genomics Basics: The Information System of Life

Think of molecular biology as a computer system with its own data, storage, and processing rules.

## DNA, RNA, and Protein: The Core Data Structures

*   **DNA (Deoxyribonucleic Acid):** This is the hard drive. It's a massive, double-stranded string of characters (`A`, `T`, `C`, `G`). It stores the permanent blueprint for everything in an organism.
    *   **Data Structure:** A very long character array/string.

*   **RNA (Ribonucleic Acid):** This is like RAM or a message queue. It's a temporary, single-stranded copy of a small segment of DNA (a gene). Its main character set is (`A`, `U`, `C`, `G`).
    *   **Data Structure:** A shorter, temporary character array/string.

*   **Protein:** This is the application or executable. It's a sequence of amino acids (20 different characters) that folds into a 3D shape to *do something*—like catalyze a reaction or form a structural component.
    *   **Data Structure:** A character array that maps to a complex 3D object.

## The Central Dogma: The Core Algorithm

This is the fundamental data flow in the cell:

**DNA → (Transcription) → RNA → (Translation) → Protein**

1.  **Transcription:** A process "reads" a gene from the DNA hard drive and creates a temporary RNA copy. It's like loading a program into memory.
2.  **Translation:** A ribosome "executes" the RNA message, reading it in 3-character chunks (codons) and assembling the corresponding protein.

## Mutations: "Bugs" in the Code

A mutation is a change in the DNA sequence. This can be:
*   **A single character change (SNP):** `A` becomes `G`.
*   **A deletion:** A character is removed.
*   **An insertion:** A new character is added.

These "bugs" can be harmless, or they can alter the final protein, causing disease. **Variant calling** is the process of finding these differences between a sample's DNA and a reference standard.

## NGS: High-Throughput Data Generation

*   **Next-Generation Sequencing (NGS):** This isn't one thing, but a collection of technologies that allow us to read DNA/RNA sequences at massive scale (gigabytes to terabytes of data per run).
    *   **Illumina:** The most common. It produces billions of short, highly accurate string reads (e.g., 150 characters long).
    *   **Nanopore:** A newer technology. It produces much longer reads (thousands of characters) but with a higher error rate. This is a classic trade-off: data volume/length vs. data accuracy.

## Common Biological Data Formats

Bioinformatics uses standardized text-based formats to store sequence data. Here are the most important ones to recognize.

### FASTA
A simple format for storing one or more sequences.
*   `>` followed by a description line.
*   The raw sequence on the following lines.

```
>sequence_1 description of my sequence
AGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATC
GATCGATCGATCGATCGATCGATC
>sequence_2 another sequence
AGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCT
```

### FASTQ
The standard format for raw NGS reads. It's a FASTA file with added quality scores.
*   `@`: Sequence identifier.
*   Line 2: The raw sequence read.
*   `+`: A separator.
*   Line 4: The quality score for each base in the sequence (ASCII encoded).

```
@SEQ_ID_1
GATTTGGGGTTCAAAGCAGTATCGATCAAATAGTAAATCCATTTGTTCAACTCACAGTTT
+
!''*((((***+))%%%++)(%%%%).1***-+*''))**55CCF>>>>>>CCCCCCC65
```

### SAM/BAM
The format for storing alignment data after mapping NGS reads to a reference genome.
*   **SAM** is human-readable text.
*   **BAM** is the compressed, binary version.
*   It's a complex, tab-delimited format with a header section (`@HD`, `@SQ`) and an alignment section.

**Example SAM line:**
```
read_1  99  chr1  713939  60  100M  =  714222  383  AGCT...  *
```

### VCF (Variant Call Format)
The format for storing genetic variations (SNPs, indels).
*   It has a meta-information header (`##`).
*   A header line (`#CHROM`).
*   Tab-delimited rows for each variant.

**Example VCF line:**
```
#CHROM  POS     ID      REF  ALT  QUAL  FILTER  INFO
chr1    100341  .       T    C    50    PASS    .
```

## Microbiome Basics for QIIME2

*   **What is a microbiome?** A community of microorganisms (bacteria, fungi, viruses) living in a particular environment (e.g., human gut, soil).
*   **How do we study it?** We can't easily culture most microbes. Instead, we sequence a specific "marker gene" that acts as a barcode for different species.
*   **16S rRNA Gene:** This is the most common marker gene for bacteria. It has regions that are the same for all bacteria, and variable regions that are different between species. By sequencing this gene, we can identify "who is there" in a sample. QIIME2 is a powerful pipeline for analyzing this type of data.

---

## 📌 **Recommended Learning Resources**

### **For Core Biology Concepts:**
*   **Khan Academy Biology:** Excellent for foundational concepts of DNA, genes, and the central dogma. [Visit here](https://www.khanacademy.org/science/biology)
*   **NCBI Bookshelf:** A free online collection of biomedical books. "The Cell: A Molecular Approach" is a great reference. [Visit here](https://www.ncbi.nlm.nih.gov/books/)

### **For Bioinformatics-Specific Theory:**
*   **Coursera - Bioinformatics for Beginners:** A good, structured overview. [Visit here](https://www.coursera.org/learn/bioinformatics-methods-1)
*   **YouTube - Omics Explained:** Short, clear videos on complex topics like NGS and different 'omics fields. [Visit channel](https://www.youtube.com/c/OmicsExplained)
*   **YouTube - The Bioinformatics Coach:** Practical tutorials and career advice. [Visit channel](https://www.youtube.com/c/TheBioinformaticsCoach)

### **For Data Formats:**
*   **FASTQ/FASTA:** [A quick visual guide](https://www.drive5.com/usearch/manual/fasta_files.html)
*   **SAM/BAM:** [SAM format specification](http://samtools.github.io/hts-specs/SAMv1.pdf) (technical but definitive)
*   **VCF:** [VCF format specification](https://samtools.github.io/hts-specs/VCFv4.2.pdf)
