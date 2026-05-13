biocorp_v2 — Conda Environment

A comprehensive conda environment for bacterial and metagenomic genomics workflows, covering the full analysis pipeline from raw reads to annotated assemblies and phylogenetic trees.

Requirements
Conda or Mamba
Python 3.10 (pinned for compatibility with bowtie2 and pysam)

System Requirements
Installed environment: ~5–8 GB
Conda package cache during install: +3–5 GB (can be cleared with conda clean -a)
SnpEff databases (per organism): 100 MB – 1 GB each
Prokka databases (BLAST, HMMER): ~2 GB
BLAST databases (nt, nr, RefSeq): 50 GB to several hundred GB
Working space per project (FASTQ, BAM, assemblies): typically 10–100 GB

Recommended free disk space
≥ 20 GB for a comfortable installation with small databases and modest projects.
≥ 50–100 GB when working with large databases (BLAST nt/nr) or multiple sequencing samples.

RAM and CPU
Minimum: 8 GB RAM, 4 CPU cores (suitable for small bacterial genomes).
Recommended: 16–32 GB RAM, 8+ CPU cores (required by SPAdes, MEGAHIT, and IQ-TREE on larger datasets).
Metagenomic assemblies with MEGAHIT or SPAdes may require 64+ GB RAM depending on sample complexity.

Operating system
Linux (x86_64) — fully supported.
macOS (Intel and Apple Silicon via Rosetta) — most tools supported; some bioconda packages may be Linux-only.
Windows — not directly supported; use WSL2 with Ubuntu.

Installation
$ conda env create -f biocorp_v2.yml
$ conda activate biocorp_v2

What's included
Quality Control: fastp, MultiQC
Read Mapping: BWA-MEM2, BWA, Bowtie2
Alignment Processing: SAMtools, BAMtools, mosdepth
Variant Calling: FreeBayes, BCFtools, VCFtools, vcflib
Variant Annotation: SnpEff, SnpSift
De Novo Assembly: SPAdes, MEGAHIT
Assembly Evaluation: QUAST
Multiple Alignment & Phylogenetics: MUSCLE, MAFFT, IQ-TREE, FastTree
Functional Annotation: Prokka, Prodigal
Sequence Utilities: BLAST, BEDTools, seqtk, Entrez Direct
Python Libraries: NumPy, Pandas, Matplotlib, Seaborn, Biopython, pysam, cyvcf2, pyvcf3

Notes
Python is pinned to 3.10 because bowtie2 and pysam do not support 3.11+.
htslib is not pinned explicitly — samtools=1.20 pulls the correct version automatically.
GNU parallel is included for parallelizing FreeBayes variant calling across genomic regions.
