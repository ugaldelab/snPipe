# snPipe
Wrapper to perform SNP calling

This software is a pipeline, written in python, to perform SNP calling for several related genomes at the same time respect to a reference genome. 

SnPipe takes a description file as input. This file must contains the description of the query genomes where the SNPs will be called. The fields of the input file are, the name of the sample, the path to the fastq files and the library type (single or paired), indicating if the library is paired_end/mate_pair or single_end. The fields must be separated by a tab.

#Input file example

strain1 /path/to/fastq1,path/to/fastq1  paired

strain1 /path/to/fastq  single

strain2 /path/to/fastq single

strain3 /path/to/fastq1,/path/to/fastq2 paired

If the query genome has more than one library, they have to be declared in different lines in the input file (strain1 in the Input example above).
