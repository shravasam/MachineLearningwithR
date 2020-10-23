# MachinelearningwithR

Install latest Rstudio : 

Step 1: Update system
sudo apt update
sudo apt -y upgrade

Step 2: Install R on Ubuntu / Debian
sudo apt -y install r-base

Step 3: Download and Install RStudio
https://rstudio.com/products/rstudio/download/#download
Choose appropriate verison.

some times you encounter dependency problems, so run:
sudo apt -f install

then run 
sudo dpkg -i rstudio-1.3.1073-amd64.deb

Step 4: Launch RStudio

for more details https://computingforgeeks.com/how-to-install-r-and-rstudio-on-ubuntu-debian-mint/
IMPORTANT ERRORS :
> install.packages('caTools')
Installing package into ‘/home/R/x86_64-pc-linux-gnu-library/3.2’
(as ‘lib’ is unspecified)
Warning in install.packages :
  package ‘caTools’ is not available (for R version 3.2.3)
  
  you must update R version from 3.2.3 to neweast version
  
  
I will explain how to set up a new project in R studio and integrate with git project