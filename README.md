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
  
  

  CLASSIFICATION MODEL IN MACHINE LEARNING IN R.
  
  ---- there are 7 model in classification in r
  
1. Logistic Regression : 
Pros:Probabilistic approach, gives informations about statistical significance of features
cons:The Logistic Regression Assumptions
2. K-Nearest Neighbors (K-NN) :
formula
library(class)
y_pred = knn(train = training_set[, -3],
             test = test_set[, -3],
             cl = training_set[, 3],
             k = 5,
             prob = TRUE)
pros:Simple to understand, fast and efficient
cons:Need to choose the number of neighbours k
3. Support Vector Machine (SVM): formula :
library(e1071)
classifier = svm(formula = Purchased ~ .,
                 data = training_set,
                 type = 'C-classification',
                 kernel = 'linear')
pros:Performant, not biased by outliers, not sensitive to overfitting
cons:Not appropriate for non linear problems, not the best choice for large number of features
4. Kernel SVM: formula :
library(e1071)
classifier = svm(formula = Purchased ~ .,
                 data = training_set,
                 type = 'C-classification',
                 kernel = 'radial')
pros:High performance on nonlinear problems, not biased by outliers, not sensitive to overfitting
cons:Not the best choice for large number of features, more complex
5. Naive Bayes: formula: 
library(e1071)
classifier = naiveBayes(x = training_set[-3],
                        y = training_set$Purchased)
pros:Efficient, not biased by outliers, works on nonlinear problems, probabilistic approach
cons:Based on the assumption that features have same statistical relevance
6. Decision Tree Classification: formula
library(rpart)
classifier = rpart(formula = Purchased ~ .,
                   data = training_set)

pros:Interpretability, no need for feature scaling, works on both linear / nonlinear problems
cons:Poor results on too small datasets, overfitting can easily occur.

7. Random Forest Classification: formula
library(randomForest)
set.seed(123)
classifier = randomForest(x = training_set[-3],
                          y = training_set$Purchased,
                          ntree = 500)
pros:Powerful and accurate, good performance on many problems including non linear.
cons:No interpretability, overfitting can easily occur, need to choose the number of trees.

TIP : CTRL + L to clear screen of console
