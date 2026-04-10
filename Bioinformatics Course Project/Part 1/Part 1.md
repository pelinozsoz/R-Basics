# Bioinformatics Course Project Part 1
This page represents a guideline for the project given by the lecturer. You can use the following libraries and functions throughout the project. Good luck!

## 🧬 Introduction of FASTA File
**What is a FASTA file?**
- A **"FASTA format"** is a simple text-format which is used for storing biological data (DNA, RNA, Protein). It stores data regarding to nucleotide or protein sequences via single-letter representations.
```r
# Example of a FASTA file
>Sequence_1 Description/Identifier
ATGCGTACGTTAGCTAGCTAGCTA
>Sequence_2 Description/Identifier
TTTGGCCAAATTACGCGCGGAA
```
**Why FASTA format is Important?**
- **Universal Standard:** It is the "default" format. If you download a sequence from NCBI or UniProt, it’s likely in FASTA.
- **Human-Readable:** Because it is plain text, you can open and edit it in any basic text editor (like Notepad or TextEdit) without special software.
- **Computational Efficiency:** Its minimalist structure (just a header and the sequence) makes it very fast for scripts to parse and process.
- **Storage Friendly:** By stripping away heavy metadata, it keeps file sizes manageable, which is vital when handling entire genomes.
- **Flexibility:** It handles both nucleotide (DNA/RNA) and protein sequences using the same logic.

**Where is it used?**
- **Sequence Alignment:** It is the mandatory input for tools like BLAST, Clustal Omega, or MAFFT to compare how similar two sequences are.
- **k-mer Analysis:** Because the sequence is continuous, it is the perfect format for breaking DNA into "k-mers" (short overlapping substrings) to analyze sequence complexity or perform assembly.
- **Structural Modeling:** Programs like AlphaFold or Modeller use FASTA files to know the exact primary sequence before predicting a 3D structure.
- **Molecular Dynamics:** It provides the initial "blueprint" for simulations in packages like NAMD or GROMACS.
- **Primer Design:** Tools like Primer3 use FASTA sequences to find the best spots for PCR primers to bind.
- **Phylogenetics:** Used to build evolutionary trees by comparing multiple FASTA files from different species.

## 🧪 Introduction to Bioconductor, BioManager and Biostrings
**1 - Bioconductor**

Bioconductor is an open-source, open-development software project for the analysis and comprehension of high-throughput genomic data. While CRAN is the general repository for all R packages, Bioconductor is the specialized "app store" specifically for biology.
- **Standardization:** It enforces strict rules so that data structures (like GRanges or SummarizedExperiment) are consistent across different packages.
- **Vast Library:** It contains thousands of packages for everything from RNA-seq and CRISPR analysis to flow cytometry and proteomics.
- **Reproducibility:** Every package is rigorously tested and documented, ensuring that your research can be replicated by others.

**2 - BiocManager**

BiocManager is the tool you use to install and manage Bioconductor packages. Because Bioconductor has its own release cycle that is tied to specific versions of R, you cannot use the standard install.packages() for everything.
- **Version Control:** It ensures that the version of the package you download is compatible with your current version of R and Bioconductor.
- **Installation:** You use the command BiocManager::install("PackageName") to fetch tools.
- **Updates:** It manages dependencies automatically, so you don't have to worry about one package breaking another.

**3 - Biostrings**

Biostrings is one of the most fundamental "workhorse" packages within Bioconductor. It provides the memory-efficient containers needed to handle large biological sequences (DNA, RNA, and Proteins) in R.
- **Efficient Memory:** Unlike standard R "character" strings, Biostrings uses "XString" objects which are optimized for biological data, allowing you to load entire genomes without crashing your RAM.
- **Reading Files:** It is the primary tool for reading and writing FASTA and FASTQ files (e.g., using readDNAStringSet).
- **Sequence Manipulation:** It includes functions for common tasks like:
   1. Complement & Reverse Complement.
   2. Translation: Converting DNA to Amino Acids.
   3. Pattern Matching: Finding specific motifs or k-mers within a sequence.

## 💻 Introduction of FASTA Files to R Studio

**1. Installation of BioStrings**

For introducing your FASTA files to R, first you have to install Biostrings package.
```r
# 1. Install BiocManager (only once)
install.packages("BiocManager")
# 2. Install Biostrings
BiocManager::install("Biostrings")
# 3. Load the package
library(Biostrings)
```

**2. Reading FASTA files**

To import sequence data, use readDNAStringSet(). It reads a FASTA file and converts it into a structured R object.
```r
# Introduce your FASTA file
fasta_path <- "path/to/your/file.fasta"
# Convert the sequence to DNAStringSet object to use Biostrings functions
your_dna_sequence <- readDNAStringSet(fasta_path)
```

**3. Calculation of Mononucleotide Conposition**

To Counts how many times each nucleotide appears, use alphabetFrequency(). It Counts all letters in the sequence.
```r
# baseOnly = TRUE --> Only counts A, T, C, G, not N, gaps, etc.)
alphabetFrequency(your_dna_sequence, baseOnly = TRUE)
# To get proportions instead of counts, use as.prob = TRUE
alphabetFrequency(your_dna_sequence, baseOnly = TRUE, as.prob = TRUE)
```
Important output!

- If you have one sequence --> vector
- If you have multiple sequences --> matrix

**4. Calculation of k-mer Conpositions**

To count all 2-letter combinations (2-mers), use dinucleotideFrequency().
```r
# Counts all possible combinations (16 total)
dinucleotideFrequency(your_dna_sequence)
```

To count all 3-letter combinations (3-mers), use trinucleotideFrequency().
```r
# Counts all possible combinations (64 total)
trinucleotideFrequency(your_dna_sequence)
```

For counting different k-mer compositions, use oligonucleotideFrequency().
```r
# General version of k-mer counting
oligonucleotideFrequency(your_dna_sequence, width = k)
```

**5. Final Steps**

- Convert your output into a data frame, merge data for different sequences.
- Save your results to a file, you can use write.csv function for that.


