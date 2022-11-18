# Intro to single cell technologies

## Requirements
Please login to the Mammouth node, we will be using the UNIX terminal to download all the software and run all the analyses.

> Note: It is required that you have some *very basic* knowledge on how to use the linux terminal as we will not go through basic unix commands in the workshop. 

## Sofware
* FastQC
* Trimmomatic
* CellRanger

> To install the software please open your terminal and copy and paste the following commands inside the text boxes. Please replae *USERNAME* with your Mammouth node login name (e.g. micm09)

### FastQC
1.	Load module
```{}
module load fastqc/0.11.9 mugqic/openjdk-jdk-19
```
2.	Check you successuflly load fastqc and you will get "FastQC v0.11.9"
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
3.	Check you successuflly load Trimmomatic and you will get "0.39"
```{}
java -jar $EBROOTTRIMMOMATIC/trimmomatic-0.39.jar -version
```

### CellRanger
1. Download cellranger and reference file
CellRanger:
```{}
wget -O cellranger-7.0.1.tar.gz "https://cf.10xgenomics.com/releases/cell-exp/cellranger-7.0.1.tar.gz?Expires=1668779973&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jZi4xMHhnZW5vbWljcy5jb20vcmVsZWFzZXMvY2VsbC1leHAvY2VsbHJhbmdlci03LjAuMS50YXIuZ3oiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE2Njg3Nzk5NzN9fX1dfQ__&Signature=SYMp58FKQ0PvMQi3bpE2hxwWLpY2TKFAwde7hIEPELykaH3QIVwNugWKyj6KLHD9EokTrIdVOJubtv3ia6DcOKepindX9EYiAsEP5AG-SzO1rHrj-FU216zgID5sefB95JceZYy4xYbPWfTxwS6TtQoCNuiktbjSi8R0f8czg5893W1kMwapy1ms7y4~HNMd6gWGPPmwmq8PnV9fyB5ovCmaCCbrDk4OXNGu65yQ953pJhLTvYfzr14D1ghFzWG-R0TfCnY2ddMCpc~3NlLStLGQwJ3mBJuolcAaTdGvLuhUFh3WR4KieMFB1r9~R0u5HcNrThsiJzr6KmvcigmQ7w__&Key-Pair-Id=APKAI7S6A5RYOXBWRPDA"
```
Reference file: 
```{}
wget https://cf.10xgenomics.com/supp/cell-exp/refdata-gex-GRCh38-2020-A.tar.gz
```
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
5.	Test you have successfully install cellranger and you will get "cellranger cellranger-7.0.1"
```{}
cellranger -V
```
