# SNPipe
This software is a pipeline, written in python, to perform SNP calling for several related genomes at the same time respect to a reference genome. The output of the pipeline is a set of VCF file containing the SNPs for each query genome. Many downstream analysis could be made with this VCF files, depending on the sort of study you are doing.

# Prerequisites

SnPipe is a pipeline that wraps several tools to perform SNP calling. Therefore, these tools must be available. Before to run SNPipe please check if the following programs are installed on the computer:

**BWA**: a mapper to align a set of reads to a reference genome.

**Samtools**: a suite to perform several operations under SAM/BAM files, such as, order, remove duplicates, transform, etc.

**FreeBayes**: an haplotype-based SNP caller.

# The input file

SnPipe takes a description file as input. This file must contains the description of the query genomes where the SNPs will be called. The fields of the input file are, the name of the sample, the path to the fastq files and the library type (single or paired), indicating if the library is paired_end/mate_pair or single_end. The fields must be separated by a tab.

Any comment in the input file is allowed.

Here there is an example of an input file:
```
strain1 /path/to/fastq1,path/to/fastq1  paired

strain1 /path/to/fastq  single

strain2 /path/to/fastq single

strain3 /path/to/fastq1,/path/to/fastq2 paired
```

If the query genome has more than one library, then they have to be declared in different lines in the input file (strain1 in the Input example above).

If the library is paired, then the path to the forward and reverse fastq files must be separated by a comma, without spaces (strain 1 and strain3 in the example above). 

# Workflow

The pipeline is straightforward. For each query genome, maps the reads, makes some filtering and performs the SNP calling. In the future, more features will be added.

The image below shows in details each step of SNPipe:

![alt tag](https://lh5.googleusercontent.com/3S0xSo8s_EDJE8k1FTtQ8RnZneoLBMSs9EsQQnbKnVP2x76OeziIUAMl1Pgn1fdIlBGV84ik1-AdE5I=w1338-h523) 
