# Intro to single cell technologies

## Requirements
Please login to the Mammouth node, we will be using the UNIX terminal to download all the software and run all the analyses.

> Note: It is required that you have some *very basic* knowledge on how to use the linux terminal as we will not go through basic unix commands in the workshop. 

## Sofware
* FastQC
* Trimmomatic
* CellRanger

> To install the software please open your terminal and copy and paste the following commands inside the text boxes. Please replace *USERNAME* with your Mammouth node login name (e.g. micm09)

### FastQC
1.	Load module
```{}
module load fastqc/0.11.9 mugqic/openjdk-jdk-19
```
2.	Check that you have successuflly load fastqc and you will get "FastQC v0.11.9"
```{}
fastqc -v
```

### Trimmomatic
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

### CellRanger
1. Download cellranger and reference file
CellRanger:
```{}
wget -O cellranger-7.0.1.tar.gz "https://cf.10xgenomics.com/releases/cell-exp/cellranger-7.0.1.tar.gz?Expires=1669691183&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jZi4xMHhnZW5vbWljcy5jb20vcmVsZWFzZXMvY2VsbC1leHAvY2VsbHJhbmdlci03LjAuMS50YXIuZ3oiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE2Njk2OTExODN9fX1dfQ__&Signature=ZFVs94nwc-NRvPAew8OPAG8EU6Mb0MbMtFb-mv0WDXV2wn~EnnNdo7jdc4snWt-OuUAg1myQayw4ocPj5tku~wxi79Pfmp~u6Hta7rGJHu3bd~B-TePDIurCOQ2eFaDhXaGII-ieEFPt8uGgUlvzmSXOxpg9FbpstHz~4gsL6cOWG9AqgknVbyevdXuhIzElEMZR3Zjpl5OzLfOK4GepmBBA0GJ7M4wiQl~H9qqzjSt4tM~wH3ND43rhW1E9qog96kxAOpmpbdI6v9Q0F9ujcRZVvFwA4X9BL~geQ5saLSUXlhts0hPT6xiutj~hY3x~9iml4YDOXbUk3sY4ePZ4ww__&Key-Pair-Id=APKAI7S6A5RYOXBWRPDA"
```
Reference file: 
```{}
wget https://cf.10xgenomics.com/supp/cell-exp/refdata-gex-GRCh38-2020-A.tar.gz
```
> if above link doesn't work, please go to https://support.10xgenomics.com/single-cell-gene-expression/software/downloads/latest get the updated link to download "Cell Ranger - 7.0.1" and human reference "References - 2020-A (July 7, 2020)". You need to register first.

3.	Unzip tar file:
```{}
tar -xzvf refdata-gex-GRCh38-2020-A.tar.gz
```
```{}
tar -xzvf cellranger-7.0.1.tar.gz
```
4.	Put cellranger to $PATH:
```{}
export PATH=/home/*USERNAME*/cellranger-7.0.1:$PATH
```
5.	Check that you have successfully install cellranger and you will get "cellranger cellranger-7.0.1"
```{}
cellranger -V
```
