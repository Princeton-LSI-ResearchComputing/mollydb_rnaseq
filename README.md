# RNA-Seq Analysis

## Input data

[Dataset: Demultiplexed fastq fileset sample GCF-MB-7361_pool18RNA from
flowcell HC232DRX3 on 2023-05-23
#1](https://htseq.princeton.edu/cgi-bin/dataset.pl?mode=view;dataset_id=2612)

## Base workflow

[snakemake-workflows/rna-seq-star-deseq2](https://snakemake.github.io/snakemake-workflow-catalog?repo=snakemake-workflows/rna-seq-star-deseq2)

### Setup and configuration

Refer to the Snakemake Workflow Catalog for more detail

1. install Snakemake and Snakedeploy

```bash
mamba create -c conda-forge -c bioconda --name snakemake snakemake snakedeploy
conda activate snakemake
```

2. deploy workflow

```bash
mkdir -p path/to/project-workdir
cd path/to/project-workdir
snakedeploy deploy-workflow https://github.com/snakemake-workflows/rna-seq-star-deseq2 . --tag v2.0.0
```

Consider putting this directory under version control.

3. configure workflow

    * `config/config.yaml`
    * `config/samples.tsv`
    * `config/units.tsv`

    * `fastq` files
    * adapter trimming
    * stradedness

4.  run workflow

```bash
snakemake --cores all --use-conda
```

5. generate report

```bash
snakemake --report report.zip
```
