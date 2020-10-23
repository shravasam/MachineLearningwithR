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
  
  HOW TO CREATE A PROJECT IN R STUDIO AND CLONE YOUR GITHUB PROJECT
  
  1. goto new project --> click on new directory-->create a folder name(create already by right click)-->then choose as sub working directory in the options-->then click on create-->the again goto new project-->click on git clone option. and clone your project..thats it.
  now your project is ready with r studio now you can commit or push into github.
  
  VERSION PROBLEMS
  
  for classification model.
  Warning in install.packages :
  package ‘ElemStatLearn’ is not available (for R version 4.0.2)

  HOW TO DEVELOP MACHINE LEARNING MODELS ?
  Before you develop any machine learning model first you need to set up data preparation/preprocessing which means encoding categorical data, missing data in the file, feature scaling which means when we develop any model we consider sample of data to send into traning and test.
  There alot of model but most used are
  1--> Regression model--> there are 6 different types of are-->Simple Linear, multiple Linear, polynomial, support vector, decision tree, random forest. I will explain each model where to use to predict the outcome.