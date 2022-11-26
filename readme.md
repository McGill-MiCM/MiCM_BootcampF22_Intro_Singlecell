# Intro to single cell technologies

## ACCESSING THE NODE
```{}
ssh username@workshop2021a.vhost37.genap.ca
```
Type in password.

## Data
1. Create a folder

```{}
mkdir intro_single_cell
cd intro_single_cell
```

2. Download data from cellranger 10x website (~ 1 minutes)

```{}
curl -O https://cf.10xgenomics.com/samples/cell-exp/3.0.0/pbmc_1k_v3/pbmc_1k_v3_fastqs.tar
```

3. Look at the copied data that you will use for the exercis
```{}
ls
```
pbmc_1k_v3_fastqs.tar

4. Extract .tar files
```{}
tar xvf pbmc_1k_v3_fastqs.tar
cd pbmc_1k_v3_fastqs
ls
```
5. Look at the fastq file
```{}
gunzip -c pbmc_1k_v3_S1_L001_I1_001.fastq.gz > pbmc_1k_v3_S1_L001_I1_001.fastq
head -n 36 pbmc_1k_v3_S1_L001_I1_001.fastq
```

### Fastqc
1.	Load module
```{}
module load fastqc/0.11.9 mugqic/openjdk-jdk-19
```

2.	Check that you have successuflly load fastqc and you will get "FastQC v0.11.9"
```{}
fastqc -v
```

3. Run the tool fastqc to assess the quality of the sequencing
```{}
fastqc pbmc_1k_v3_S1_L001_I1_001.fastq.gz
```

