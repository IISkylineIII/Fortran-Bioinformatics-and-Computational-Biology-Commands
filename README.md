# Fortran Bioinformatics and Computational Biology Commands

## Description  
This repository provides a comprehensive collection of Fortran scripts and code snippets commonly used in Bioinformatics and Computational Biology. It aims to support researchers and students in performing efficient sequence analysis, structural computations, statistical modeling, and numerical simulations using Fortran’s high-performance capabilities.

## Pipeline Overview  
The collection is organized into key functional areas relevant to bioinformatics workflows:

### 1. Data Input and Preprocessing  
- Reading and writing sequence data files (FASTA, PDB)  
- Parsing text and numerical data formats  
- Basic string and array manipulations for data cleaning

### 2. Sequence and Structural Analysis  
- DNA/RNA/protein sequence manipulation (complement, reverse, translation)  
- Pairwise and multiple sequence alignments  
- Molecular structure calculations and format conversions (e.g., PDB parsing)

### 3. Numerical and Statistical Methods  
- Statistical computations (mean, variance, correlation)  
- Matrix operations and linear algebra (essential for population genetics and phylogenetics)  
- Random number generation and Monte Carlo simulations

### 4. Phylogenetics and Evolutionary Modeling  
- Distance matrix calculation  
- Tree construction algorithms (UPGMA, Neighbor Joining)  
- Simulation of nucleotide substitution models

### 5. Visualization and Output  
- Generating formatted output files for visualization tools  
- Basic plotting data preparation (to be used with external tools)  

## Example Commands and Usage

### Reading FASTA file  
```fortran
program read_fasta
  implicit none
  character(len=100) :: line
  integer :: iostat
  open(unit=10, file='sequence.fasta', status='old')
  do
    read(10, '(A)', iostat=iostat) line
    if (iostat /= 0) exit
    print *, trim(line)
  end do
  close(10)
end program read_fasta

```
### Computing GC content
```
subroutine matmul_example(A, B, C, n)
  integer, intent(in) :: n
  real, intent(in) :: A(n,n), B(n,n)
  real, intent(out) :: C(n,n)
  integer :: i,j,k
  C = 0.0
  do i = 1, n
    do j = 1, n
      do k = 1, n
        C(i,j) = C(i,j) + A(i,k)*B(k,j)
      end do
    end do
  end do
end subroutine matmul_example
```

### Requirements
* Fortran compiler (gfortran, ifort, etc.)
* Basic command line environment (Linux, macOS, Windows WSL)

### References
* Fortran 95/2003 Language Documentation
* Bioinformatics Algorithms: An Active Learning Approach – Phillip Compeau & Pavel Pevzner
* Numerical Recipes in Fortran – William H. Press et al.

### License
MIT License
