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

2.	Check that you have successuflly load fastqc
```{}
fastqc -v
```

3. Run the tool fastqc to assess the quality of the sequencing
```{}
fastqc pbmc_1k_v3_S1_L001_I1_001.fastq.gz
```

4.  To make it easier, let’s look at the FASTQC results on your web browser 
```{}
mkdir ~/public_html
cp ~/intro_single_cell/pbmc_1k_v3_fastqs/*.html ~/public_html/
chmod -R 755 ~
```
You can now access your files from a web browser at (by replacing “XX” by your username):
https://workshop2021a.vhost37.genap.ca/~micmXX

### Cellranger
1. Load module
```{}
source $EBROOTCELLRANGER/sourceme.bash
```

2.	Check that you have successuflly load cellranger
```{}
cellranger --version
```

3. Download reference (~ 5mins)
```{}
cd ..
wget https://cf.10xgenomics.com/supp/cell-exp/refdata-gex-GRCh38-2020-A.tar.gz
tar -zxvf refdata-gex-GRCh38-2020-A.tar.gz
```

4. Run cellranger count (~hours)
```{}
cellranger count --id=run_count_1kpbmcs \
   --fastqs=/home/micm08/intro_single_cell/pbmc_1k_v3_fastqs \
   --sample=pbmc_1k_v3 \
   --transcriptome=/home/micm08/intro_single_cell/refdata-gex-GRCh38-2020-A
```

5. You can check the outputs from official website:
https://www.10xgenomics.com/resources/datasets/1-k-pbm-cs-from-a-healthy-donor-v-3-chemistry-3-standard-3-0-0
