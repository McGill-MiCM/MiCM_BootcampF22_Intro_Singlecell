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

### Fastqc
1. Load StdEnv
```{}
module load StdEnv/2020
```
2. Load Trimmomatic
```{}
module load trimmomatic/0.39
```
3.	Check that you have successuflly load Trimmomatic and you will get "0.39"
```{}
java -jar $EBROOTTRIMMOMATIC/trimmomatic-0.39.jar -version
```
