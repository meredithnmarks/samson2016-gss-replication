
This document outlines the steps needed to reproduce the results of my replication project, which 
is based on the study Support for immigration reduction and physician distrust in the United 
States, published in 2016 by Frank L Samson. 

For this project, I used RStudio version 4.4.2 

To reproduce the results of this paper:  

1. Download “gss2012.RDS” into a folder and set this folder as your working directory in R.  
2. Download all script files into that same folder:
 
  a. mmarks9-PDIR-01-mgmt-setup ** 
  b. mmarks9-PDIR-02-mgmt-revcode ** 
  c. mmarks9-PDIR-03-mgmt-missval ** 
  d. mmarks9-PDIR-04-mgmt-table1var ** 
  e. mmarks9-PDIR-05-analysis-desc 
  f. mmarks9-PDIR-06-mgmt-impute ** 
  g. mmarks9-PDIR-07-mgmt-scale ** 
  h. mmarks9-PDIR-08-analysis-table1scale 
  i. mmarks9-PDIR-09-analysis-OLSreg 
  j. mmarks9-PDIR-10-analysis-OLRreg
  
**denotes a data management file 
4. Open scripts in R.  
5. Install packages: dplyr, mice, ordinal 
6. Run scripts in order listed above. 
