# Intro to single cell technologies

## Requirements
Please login to the Mammouth node, we will be using the UNIX terminal to download all the software and run all the analyses.

> Note: It is required that you have some *very basic* knowledge on how to use the linux terminal as we will not go through basic unix commands in the workshop. 

## Sofware
* Trimmomatic
* CellRanger

> To install the software please open your terminal and copy and paste the following commands inside the text boxes. Please replae *USERNAME* with your Mammouth node login name.

### Download Trimmomatic
1.	Please download “binary” file of Trimmomatic 
```{}
wget http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/Trimmomatic-0.39.zip
```
2.	Unzip file and you will get “Trimmomatic-0.39” folder.
```{}
unzip Trimmomatic-0.39.zip
```
4.	Navigate to Trimmomatic-0.39 folder
```{}
cd /home/*USERNAME*/Trimmomatic-0.39
```
4.	Type below code in terminal and press “Enter”, you will get “0.39” means you have downloaded trimmomatic successfully.
```{}
java -jar trimmomatic-0.39.jar -version
```

### Mac OS
First install [Homebrew](https://brew.sh/) or any other package manager.
```{}
wget http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/Trimmomatic-0.39.zip 
```
Then you can use brew to install the packages.
```{}
wget -O cellranger-7.0.1.tar.gz "https://cf.10xgenomics.com/releases/cell-exp/cellranger-7.0.1.tar.gz?Expires=1668778645&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jZi4xMHhnZW5vbWljcy5jb20vcmVsZWFzZXMvY2VsbC1leHAvY2VsbHJhbmdlci03LjAuMS50YXIuZ3oiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE2Njg3Nzg2NDV9fX1dfQ__&Signature=XixQauaIqvgbegK9rSzldX-WM20EoTT4k0MnkVhFrZT8zThfm8yl5NeiHjFLQO3DXiEWuwzZhexdKFqbmw~Q4w7ZMkSru2iVgdJ3BRJaHOovGWape25izgUpJCx0uNQxf40DZ76TSXMz8Qi0uhCyfT5lMETku4Ucj1cDBXmxNF2U2YjUZ3Z0mC7Zfe4UCEHczjusquO6LWo~-3IOHeBPFMH7GiXvfFTLIB7qzFZQeY7VMovbILDtTnUWE3xGRARQTxGJJZ3Fl6QYr3MSbr3dBatj-jGGtzAmM-ly6xREhb5Mba3z-rnJF1YwEXuf8wsTVwuX1Yrd6kCwBhX29QpE-g__&Key-Pair-Id=APKAI7S6A5RYOXBWRPDA"
```

### Check the installation
To check that the program works, you can check if the help message gets printed:
```{}
fastqc --help
bowtie2 --help
samtools --help
multiqc --help
cutadapt --help
```

> Some problems may arise while installing software. Be patient and read the error message, it could be due to some dependecies missing. Googling the error message is a good first attempt to solve it.
