# **Introduction**

This project takes Laverdonk trial data from the Azure data warehouse and prepares it
for data analysis. Output of the scripts are excel files for the end users to 
analyse in their prefered statical programs. 

## *Input*

Data from the various Laverdonk trials is directly stored in an SQL Azure data warehouse
maintained by FarmResult. Over fifty poultry and over hundred pig dataframes are stored 
in this data warehouse. The current project meaningfully merges these dataframes 
for further processing in analyses. 

### Access

In order to access the data in the data warehouse, your IP adress needs to be 
added to the server's secure list. By sending an email with the server's name 
`prd-datahub-76qbhnv5jf4a4` and your IP adress to [?????](????@agrifirm.com), 
access can be obtained. 

## *Output*

At the end of the scripts, tables and graphs are exported for further analyses.

Note that two sets of folders are created, one NL and one EN. Those folder contain
the same files (with the same names) with the only difference that NL contains files
with the Dutch regional settings (decimal seperator is a comma and thousands seperator is a dot)
whereas the EN folder contains files with English settings (where decimal seperator is a dot and
thousands seperator is a comma). This allows everyone to properly open the files, 
regardless of their computer's regional settings. 

# Package usage

The scripts in the current project use functions from various packages. In order to
ensure the scripts can be run after new R install, the packages are loaded using
a generic substitue for `library` and `require`, namely `p_load`. This generic function
from the package `pacman` will open one or more packages and install it when the 
packages isn't available locally. *Note, however, that it will always install the
most recent package version, which might be different from the version the current
project was build upon.* In other words, using the generic load function that also
installs the packages when they are not locally available might result in errors
when functions previously available in a package have been deprecated in the newer
package version.

## *Install an older package version*

Although different approaches can be used ([see for example here on Stackoverflow](https://stackoverflow.com/questions/17082341/installing-older-version-of-r-package)),
the easiest way appears to be using the `devtools` package. For instance, in order
to install an older version of `ggplot` use:

```
require(devtools)
install_version("ggplot2", version = "0.9.1", repos = "http://cran.us.r-project.org")
```

## *Package overview*

Below you will find a list of all individual packages loaded in the scripts, with
the version number we last checked the scripts worked for. Note that the scripts
might still work with newer package versions. 

- pacman 0.5.1
- tidyverse 1.3.0, specifically:
  * ggplot2 3.3.3
  * dplyr 1.0.5
  * purrr 0.3.4
- lubridate 1.7.10
- DBI 1.1.1
- rstudioapi 0.13 
- odbc 1.3.1
- grid 4.0.3
- plyr 1.8.6 
- scales 1.1.1
- DataCombine 0.2.21
- RPostgreSQL 0.6-2 
- reshape2 1.4.4 
- stringr 1.4.0
- broom 0.7.5

# Folder structure

The project contains several subfolders:

- GeneralFunctions: This folder contains scripts with (poultry and pig) functions 
that are used in multiple branch specific scripts.

- LavisMonitoringAndStatistics: General folder that contains the poultry and pig 
specific scripts. Note that each branch has its own subfolder with scripts. 

## *Pigs*

To prepare the pigs data, distinction is made between the piglet phase and growth 
finisher phase. Both phases have their own set of scripts. 

## *Poultry*
In order to prepare the poultry data, a distinction is made between the broiler
and layers data. In addition, depending on the experimental desing, the layers data can be prepared using 24 or 48 pens.

# Questions

Questions regarding the scripts can be addressed by members of the Data Science Team. 
Practical questions, for example regarding the meaning of certain data or regarding
specific trials, can be adressed to [Marijke Ubbink - Blanksma](m.ubbink@agrifirm.com)
or [Susanne van Uden](s.vanuden@agrifirm.com).
