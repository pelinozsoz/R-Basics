# Bioinformatics Course Project Part 2

## 🧬 Introduction to Differential index
**What is differential index?**

A differential index is a way of comparing features between two biological sequences or datasets to highlight what is different between them.
Those **"features"** can be:
- k-mers 
- gene expression values
- nucleotide frequencies

### Step 1: Load your data
```r
library(Biostrings)

fasta1 <- readDNAStringSet("file1.fasta")
fasta2 <- readDNAStringSet("file2.fasta")

#readDNAStringSet() → reads DNA sequences from FASTA
#[[1]] → takes the first sequence
#as.character() → converts it to plain text
```
### Step 2: Determine the kmer positions 
```r
kmer_positions <- function(seq, k) {
*your code*
}
```
Your code should contain a loop which can extract kmers and determine their positions (indexes). So that it returns as a kmer list.
```r
#Example:
seq = "ATAT"
k = 2

#It will return as
| i | k-mer |
| - | ----- |
| 1 | AT    |
| 2 | TA    |
| 3 | AT    |

#Which in turn gives the output of:
"AT" → [1, 3]
"TA" → [2]
```
### Step 3: Compute Position Differences
```r
compute_differential_index <- function(pos1, pos2) {
  *your code*
}
```
Your code should take positions from seq1 and seq2 and compute all k-mer-wise differences.
### Step 4: Find the most common differential index
```r
analyze_global_shift <- function(seq1, seq2, k) {
  
  pos1 <- get_kmer_positions(seq1, k)
  pos2 <- get_kmer_positions(seq2, k)
  
  *your code*
}
```
Your code should find the most common differential index to determine the optimal shift.
