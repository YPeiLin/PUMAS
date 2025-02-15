# PUMAS
Fine-tuning polygenic risk score models using GWAS summary statistics

## Introduction

Our project gives user-friendly function that presents a direct and explicit result of fine-tuning polygenic risk score models. For full explanation and tutorial, please go to  [wiki](https://github.com/qlu-lab/PRS-Fine-tuning/wiki)

### Prerequisites
R
The following R packages are required
`devtools`
`PRS-Fine-tuning` 

If you don't have devtools installed, please install as following
##### Mac and Linux:
```
devtools::install_github("hadley/devtools")
```
##### Windows:
```library(devtools)
build_github_devtools()

#### Restart R before continuing ####
install.packages("devtools.zip", repos = NULL)

# Remove the package after installation
unlink("devtools.zip")
```
Then, load the package
```
library(devtools)
```

### Step 0
Downloading PUMAS on working directory

In R, type the following command in console
```
install_github("qlu-lab/PUMAS")
```


## Input Data
We requires an input file in a form of csv including those values. The file name is T0030_pruned.txt in our case.

| Parameter                   | Parameter Usage | Description                                                                  |
|----------------------------|----------------|------------------------------------------------------------------------------|
| Beta            |  data.real$Beta     |  Beta value retrieved from GWAS|
| MAF         | data.real$EAF          |    Minor allele frequency retrieved from GWAS      |
| Se              | data.real$SE        |       Standard Error  retrieved from GWAS             |                                         
| Sample          |N.sample=766345 | Sample size that we are interested in |

The input line should be in /Your-Wokring-directory/PUMAS/input

## Output Data
The output will be a png file, for full interpretations please see details in [wiki](https://github.com/qlu-lab/PRS-Fine-tuning/wiki) page.
![Test Image 4](https://github.com/qlu-lab/PRS-Fine-tuning/blob/master/PRS-Fine-tuning/result/T0030_pruned.png)

### Step 1
After loading the library devtools and downloading our libraries.

```
devtools::load_all(PUMAS)
```
If you are having trouble with working directory, go to menu of R > Build > Load All

### Step 2
Giving input infortion to do an analysis from our package. In our example,, see details in [wiki](https://github.com/qlu-lab/PUMAS/wiki) 
```
pumas.main("/working-directory/PUMAS/PRS-Fine-tuning/input/T0030_pruned.txt","Beta","EAF","SE",766345,TRUE)
```


## Authors

See also the list of [contributors](##) who participated in this project.

## License

All rights reserved for [Lu-Laboratory](http://qlu-lab.org/)

## Citation

If you use the package, please cite

[Zhao, Z. et al. Fine-tuning Polygenic Risk Scores with GWAS Summary Statistics. bioRxiv, 810713 (2019).](https://www.biorxiv.org/content/10.1101/810713v1)

## Acknowledgments


