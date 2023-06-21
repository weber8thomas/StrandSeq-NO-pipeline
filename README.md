# StrandSeq-NO-pipeline

Small snakemake pipeline to visualise Nucleosome Occupancy using ngsplot tool.

1. Create a directory and symlink your samples processed using [ashleys-qc-pipeline](https://github.com/friendsofstrandseq/ashleys-qc-pipeline)

```
mkdir /scratch/TEST & cd /scratch/TEST
ln -s /scratch/DATA/sample_1 .
ln -s /scratch/DATA/sample_2 .
ln -s /scratch/DATA/sample_3 .
```

2. Modify configuration

Open `config/config.yaml`, modify the `dir` (here `/scratch/TEST`) and the comparisons list to be processed. Each comparison must correspond to new entry (defined by a `-`) where all samples are specified without quotes and separated by a `,` (NO SPACES!)

3. Run the pipeline

```
snakemake --profile workflow/snakemake_profiles/HPC/slurm_EMBL
```