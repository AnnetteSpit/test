# Introduction 

This project takes Laverdonk trail data from the Azure data warehouse and prepares it
for data analysis. Output of the scripts are excel files for the end users to 
analyse in their prefered statical programs. 

# Package usage

The scripts in the current project use functions from various packages. In order to
ensure the scripts can be run after new R install, the packages are loaded using
a generic substitue, namely `p_load`, for `library` and `require`. This generic function
from the package `pacman` will open one or more packages and install it when the 
packages isn't available locally. Note, however, that it will always install the
most recent package version, which might be different from the version the current
script was build upon. In other words, using the generic load function that also
installs the packages when they are not locally available might result in errors
when functions previously available in a package have been deprecated in the newer
package version.

## Install an older package version

Although different approaches can be used ([see for example here on Stackoverflow](https://stackoverflow.com/questions/17082341/installing-older-version-of-r-package)),
the easiest way appears to be using the `devtools` package. For instance, in order
to install an older version of `ggplot` use:

```
require(devtools)
install_version("ggplot2", version = "0.9.1", repos = "http://cran.us.r-project.org")
```

## Package overview 
- pacman
- tidyverse 
..* ggplot2
..* dplyr
..* purrr
- lubridate
- DBI
- rstudioapi 
- odbc
- grid
- plyr
- scales
- DataCombine
- RPostgreSQL
- reshape2
- stringr

# Folder structure

The project contains several subfolders:

- GeneralFunctions: This folder contains scripts with (poultry and pig) functions 
that are used in multiple branch specific scripts.

- LavisMonitoringAndStatistics: General folder that contains the poultry and pig 
specific scripts. Note that each branch has its own subfolder with scripts. 

## Pigs

To prepare the pigs data, distinction is made between the piglet phase and growth 
finisher phase. Both phases have their own set of scripts. 

## Poultry
In order to prepare the poultry data, a distinction is made between the broiler
and layers data. In addition, the layers data can be prepared using 24 or 48 pens.
This depends on the experimental design. 

# Questions

Questions regarding the scripts can be addressed by members of the Data Science Team. 
Practical question can be adressed to [Marijke Ubbink - Blanksma](m.ubbink@agrifirm.com)
and [Susanne van Uden](s.vanuden@agrifirm.com).
