# MVP [![](https://img.shields.io/badge/Issues-1%2B-brightgreen.svg)](https://github.com/XiaoleiLiuBio/MVP/issues) [![](https://img.shields.io/badge/Release-v1.0.1-blue.svg)](https://github.com/XiaoleiLiuBio/MVP/commits/master)
## A Memory-efficient, Visualization-enhanced, and Parallel-accelerated Tool For Genome-Wide Association Study
### Installation
**MVP** is only available on GitHub, and can be installed using **devtools**. Two packages should be installed beforehand, **snpStats** and **rfunctions** (only accepts **RcppEigen** <= "0.3.2.9.0"). **MVP** can be installed with the following R code:
```r
#if "devtools" isn't installed, please "install.packages(devtools)" first.
install_version('RcppEigen', version = "0.3.2.9.0")
devtools::install_github("Bioconductor-mirror/snpStats")
devtools::install_github("jaredhuling/rfunctions")
devtools::install_github("xiaoleiLiubio/MVP")
```
After installed successfully, **MVP** can be loaded with the following R code:
```r
library(MVP)
```
Typing ```?MVP``` could get the details of all parameters.

### Data Preparation

If you have genotype data in **PLINK** format (bed/bim/fam):<br>
**fileBed** is a string, the name of genotype data in PLINK format<br>
**fileKin** is "TRUE" or "FALSE", if true, a kinship matrix represents relationship among individuals will be calculated<br>
**filePC** is "TRUE" or "FALSE", if true, principal component analysis will be performed<br>
**out** is a string, the name of output file<br>
**priority** is "speed" or "memory", the 'speed' mode is faster but uses more memory while 'memory' is slower but uses less memory<br>
**maxLine** is a number, if **priority = "memory"**, it is the number of markers read into memory<br>

```r
MVP.Data(fileBed="plink",
         filePhe=NULL,
         fileKin=FALSE,
         filePC=FALSE,
         out="mvp.plink",         
         #priority="memory",
         #maxLine=10000,
)
```
If you have genotype data in **PLINK** format (bed/bim/fam):<br>
**fileHMP** is a string or a string vector, e.g. fileHMP = "hapmap.txt" or fileHMP = c("chr1.hmp.txt", "chr2.hmp.txt", chr3.hmp.txt)<br>
**filePhe** is 
**fileKin** is "TRUE" or "FALSE", if true, a kinship matrix represents relationship among individuals will be calculated<br>
**filePC** is "TRUE" or "FALSE", if true, principal component analysis will be performed<br>
**out** is a string, the name of output file<br>
**priority** is "speed" or "memory", the 'speed' mode is faster but uses more memory while 'memory' is slower but uses less memory<br>
**maxLine** is a number, if **priority = "memory"**, it is the number of markers read into memory<br>

```r
MVP.Data(fileHMP="hapmap.txt",
    filePhe="phenotype.txt",
    fileKin=FALSE,
    filePC=FALSE,
    out="mvp.hmp",
    #maxLine=10000,
    #priority="memory"
)
```




