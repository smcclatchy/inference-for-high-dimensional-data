---
layout: page
title: Setup
permalink: /setup/
---
## Installation

R is a programming language that is especially powerful for data exploration, 
visualization, and statistical analysis. To interact with R, we use RStudio. 

1. Install the latest version of R from [CRAN](https://cran.r-project.org/). 
If you are using a JAX-owned machine, you can use the JAX Self Service app 
instead without needing support from the IT help desk.

2. Install the latest version of RStudio [here](https://www.rstudio.com/products/rstudio/download/). Choose the free 
RStudio Desktop version for Windows, Mac, or Linux. If you are using a 
JAX-owned machine, you can use the JAX Self Service app instead without needing 
support from the IT help desk.

3. Start RStudio. We will use several packages from CRAN. You can install them 
from the Console or from the Install button on the RStudio Packages tab. 
Copy-paste this list of packages into the Install dialog box: 

devtools, BiocManager, here, rafalib, lasso2, matrixStats

Alternatively, run the following in the Console.

~~~
    install.packages(c("devtools", "BiocManager", "here", "rafalib", "lasso2", "matrixStats"))
~~~
{: .r}

 4. Once you have installed the packages, load the libraries by checking the box 
next to each package name on the Packages tab, or alternatively running this 
code in the Console for each package.

    ~~~
    library(devtools)
    ~~~
    {: .r}

    Repeat the command above with the other packages you just installed.

5. We will also use packages available only on Github. Once the devtools library 
is loaded you will be able to install packages from Github using 
`install_github()`. You must install  these packages from the Console. They will 
not be  available from the RStudio Packages tab.

    ~~~
    install_github(c("genomicsclass/GSE5859Subset", "genomicsclass/GSE5859",
  "genomicsclass/maPooling", "genomicsclass/tissuesGeneExpression"))
    ~~~
    {: .r}

6. Once you have installed the packages, load the libraries by running this 
code in the Console.

    ~~~
    library(GSE5859Subset)
    ~~~
    {: .r}

    Repeat for each of the packages installed from Github.

7. Finally, we will use Bioconductor packages. Install these packages in the 
Console:

    ~~~
    BiocManager::install(c("genefilter", "SpikeInSubset", "SummarizedExperiment", "parathyroidSE", "Biobase", "limma", "qvalue", "PCAtools"))
    ~~~
    {: .r}

8. Once you have installed the Bioconductor packages, load the libraries by 
running this code in the Console.

    ~~~
    library(genefilter)
    ~~~
    {: .r}

Repeat for each of the packages installed from Bioconductor.

## Data files and project organization

1. Make a new folder in your Desktop called `inference`. Move into this new 
folder.

2. Create  a `data` folder to hold the data, a `scripts` folder to house your scripts, and a `results` folder to hold results. 

Alternatively, you can use the R console to run the following commands for steps 
1 and 2.
~~~
setwd("~/Desktop")
dir.create("./inference")
setwd("~/Desktop/inference")
dir.create("./data")
dir.create("./scripts")
dir.create("./results")
~~~
{: .r}

Please download the following file and place it in your `data` folder. You 
can download the file from the URL below and move the file the same way that 
you would for downloading and moving any other kind of data.

Alternatively, you can copy and paste the following into the R console to 
download the data.
~~~
download.file(url = "https://raw.githubusercontent.com/genomicsclass/dagdata/master/inst/extdata/femaleControlsPopulation.csv", destfile = "data/femaleControlsPopulation.csv")
~~~
{: .r}


{% include links.md %}
