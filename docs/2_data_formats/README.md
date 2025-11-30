# 2. Data Formats: The "File Types" of Bioinformatics

To work with biological data, you need to parse its standard file formats. Here are the most common ones you'll encounter.

## FASTA (`.fa`, `.fasta`)

The simplest format. It's used for storing one or more sequences (DNA, RNA, or protein). A file containing multiple FASTA sequences is often called a "multi-FASTA" file.

*   **Structure:**
    1.  A header line that starts with `>`. This line contains the sequence ID and optional metadata.
    2.  The raw sequence data on one or more subsequent lines.

*   **Example:**
    ```
    >sequence1_id description of sequence
    AGTCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGA
    TCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATC
    >sequence2_id another sequence, different length
    AGCTAGCTAGCTAGCT
    ```

## FASTQ (`.fq`, `.fastq`)

The standard format for raw NGS data from sequencers. It's an extension of FASTA that adds a quality score for each base.

*   **Structure:** Always 4 lines per sequence read.
    1.  Line 1: Starts with `@`, containing the sequence ID.
    2.  Line 2: The raw sequence data (the "read").
    3.  Line 3: Starts with `+`, and is sometimes followed by the same sequence ID again.
    4.  Line 4: A string of ASCII characters representing the quality score for each base.

*   **What is the Quality Score?**
    It's a measure of the probability that the base was called incorrectly. The score is `Q = -10 * log10(P)`, where `P` is the error probability. A higher score means a more reliable base call. The score is encoded as an ASCII character to save space. For example, `!` is a low score, while `J` is a high score.

*   **Example:**
    ```
    @read_id_from_sequencer
    GATTACAAGATAGATAGATAGATAG
    +
    !''*((((***+))%%%++)(%%%%
    ```

## SAM/BAM (`.sam`, `.bam`)

Sequence Alignment Map format. It is the universal format for storing results from mapping reads to a reference genome.

*   **SAM:** A human-readable, tab-delimited text file.
*   **BAM:** The binary, compressed, and indexed version of SAM. It's not human-readable and is what you'll use for most computational analyses because it's much more efficient.

A SAM file has a header section (lines start with `@`) and an alignment section where each row is a read.

*   **Example SAM line:**
    `read_76  99  chr1  10050  60  100M  =  10250  300  AGCT...  FFFF...`

*   **Key columns:**
    *   `read_76`: ID of the read.
    *   `99`: A bitwise FLAG indicating properties of the alignment (e.g., read is paired, mapped in proper pair).
    *   `chr1`: Reference sequence name (chromosome).
    *   `10050`: 1-based leftmost mapping POSition.
    *   `60`: MAPping Quality (MAPQ).
    *   `100M`: CIGAR string, indicating how the read aligns (100 matches/mismatches).

## VCF (`.vcf`)

Variant Call Format. This file stores information about genetic variations (where a sample's DNA differs from the reference genome).

*   **Structure:** A tab-delimited file with a header section (lines start with `##`) and a content section.
*   **Example VCF line:**
    `chr1  10591  rs12345  A  G  100  PASS  DP=40;AF=0.5`
*   **Key columns:**
    *   `chr1`: Chromosome.
    *   `10591`: Position on the chromosome.
    *   `rs12345`: ID of the variant (often from a database like dbSNP).
    *   `A`: The REFerence base.
    *   `G`: The ALTernate base found in the sample.
    *   `100`: QUALity score for the assertion.
    *   `PASS`: FILTER status.
    *   `DP=40;AF=0.5`: INFO field with more details (e.g., read depth, allele frequency).

## GFF/GTF (`.gff`, `.gtf`)

General Feature Format. Used to store genome annotations. It describes where genes, exons, introns, etc., are located on a genome. GTF is a stricter version of GFF.

*   **Structure:** A 9-column, tab-delimited file.
*   **Example GTF line:**
    `chr1  ENSEMBL  exon  11869  12227  .  +  .  gene_id "ENSG00000223972"; transcript_id "ENST00000456328"; ...`
*   **Key columns:**
    1.  `seqname`: Chromosome or contig.
    2.  `source`: Program that generated the feature.
    3.  `feature`: The feature type (e.g., `gene`, `exon`, `CDS`).
    4.  `start`: Start position.
    5.  `end`: End position.
    6.  `score`: A score.
    7.  `strand`: `+` or `-`.
    8.  `frame`: For coding sequences (CDS).
    9.  `attribute`: A semicolon-separated list of tags and values with more information.

## BED (`.bed`)

Browser Extensible Data format. A simple and flexible format for defining genomic regions. It's often used to represent ChIP-seq peaks, regions of interest, or gene locations for visualization in a genome browser like IGV or UCSC Genome Browser.

*   **Structure:** A tab-delimited file with at least 3 columns.
*   **Example BED line (3 columns):**
    `chr1   10000   10500`
*   **Core columns:**
    1.  `chrom`: Chromosome name.
    2.  `chromStart`: Start position (0-based).
    3.  `chromEnd`: End position (1-based).
    *   Optional columns can provide a `name`, `score`, `strand`, and more.
