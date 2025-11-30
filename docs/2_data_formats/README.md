# 2. Data Formats: The "File Types" of Bioinformatics

To work with biological data, you need to parse its standard file formats. Here are the most common ones you'll encounter.

## FASTA (`.fa`, `.fasta`)

The simplest format. It's used for storing sequence data (DNA, RNA, or protein).

*   **Structure:**
    1.  A header line that starts with `>`. This line contains the sequence ID and optional metadata.
    2.  The raw sequence data on one or more subsequent lines.

*   **Example:**
    ```
    >sequence1_id description of sequence
    AGTCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGA
    TCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATC
    ```

## FASTQ (`.fq`, `.fastq`)

The standard format for raw NGS data. It's an extension of FASTA that adds a quality score for each base.

*   **Structure:** Always 4 lines per sequence read.
    1.  Line 1: Starts with `@`, containing the sequence ID (like FASTA's `>`).
    2.  Line 2: The raw sequence data.
    3.  Line 3: Starts with `+`, and is sometimes followed by the same sequence ID again.
    4.  Line 4: A string of ASCII characters representing the quality score for each base in the sequence. Each character encodes a Phred quality score.

*   **Example:**
    ```
    @read_id_from_sequencer
    GATTACAAGATAGATAGATAGATAG
    +
    !''*((((***+))%%%++)(%%%%
    ```

## SAM/BAM (`.sam`, `.bam`)

Sequence Alignment Map format. It stores information about how your sequence reads (from a FASTQ file) map to a reference genome.

*   **SAM:** A human-readable, tab-delimited text file. Each row represents a single read alignment. It has a header section (starting with `@`) and an alignment section.
*   **BAM:** The binary, compressed, and indexed version of SAM. It's not human-readable and is what you'll use for most computational analyses because it's much more efficient.
    *   Analogy: `SAM` is to `BAM` as `JSON` is to `BSON` or a binary protocol buffer.

## VCF (`.vcf`)

Variant Call Format. This file stores information about genetic variations (where an individual's DNA differs from the reference genome).

*   **Structure:** A tab-delimited file that lists positions in a genome and the variation found at that position (e.g., a `C` instead of a `T`). It includes metadata about the confidence, depth, and type of variation.
