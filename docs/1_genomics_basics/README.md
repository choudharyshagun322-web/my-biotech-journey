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

## NGS: High-Throughput Data Generation

*   **Next-Generation Sequencing (NGS):** This isn't one thing, but a collection of technologies that allow us to read DNA/RNA sequences at massive scale (gigabytes to terabytes of data per run).
    *   **Illumina:** The most common. It produces billions of short, highly accurate string reads (e.g., 150 characters long).
    *   **Nanopore:** A newer technology. It produces much longer reads (thousands of characters) but with a higher error rate. This is a classic trade-off: data volume/length vs. data accuracy.
