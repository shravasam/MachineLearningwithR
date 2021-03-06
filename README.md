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
  
  

  #CLASSIFICATION MODEL IN MACHINE LEARNING IN R.
  
  ---- there are 7 model in classification in r
  
1. Logistic Regression : 
Pros:Probabilistic approach, gives informations about statistical significance of features
cons:The Logistic Regression Assumptions
classifier = glm(formula = Purchased ~ .,
                 family = binomial,
                 data = training_set)
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

#CLUSTERING MODELS IN MACHINE LEARNING IN R

There are two types of clustering models
  1.K means: formula :
  --Fitting K-Means to the dataset
set.seed(29)
kmeans = kmeans(x = dataset, centers = 5)
y_kmeans = kmeans$cluster
  2.Hierarchical Clustering: formula
  dendrogram = hclust(d = dist(dataset, method = 'euclidean'), method = 'ward.D')
plot(dendrogram,
     main = paste('Dendrogram'),
     xlab = 'Customers',
     ylab = 'Euclidean distances')



  
  #NATURAL LANGUAGE PROCESSING (NLP)
  ---> Install the below  packages
  install.packages('tm') to install this package there is 
  install.packages('SnowballC')
  
  If you find the below error while installing above package "tm".

  If libxml-2.0 is already installed, check that 'pkg-config' is in your
PATH and 
PKG_CONFIG_PATH contains a libxml-2.0.pc file. If pkg-config is unavailable you can set INCLUDE_DIR and LIB_DIR manually via:
R CMD INSTALL --configure-vars='INCLUDE_DIR=... LIB_DIR=...'

Please run below commands in console.

install R developer packages using below commands
Installing System Dependencies for devtools :
sudo apt-get install build-essential libcurl4-gnutls-dev libxml2-dev libssl-dev
Installing the Devtools Package
sudo -i R


important point to be noted 
 you use classification algorithms to classify language. Speaking of classification algorithms, most of NLP algorithms are classification models, and they include Logistic Regression, Naive Bayes, CART which is a model based on decision trees, Maximum Entropy again related to Decision Trees, Hidden Markov Models which are models based on Markov processes.


#DEEP LEARNING IN R

Deep Learning is the most exciting and powerful branch of Machine Learning. Deep Learning models can be used for a variety of complex tasks:

    Artificial Neural Networks for Regression and Classification
    Convolutional Neural Networks for Computer Vision
    Recurrent Neural Networks for Time Series Analysis
    Self Organizing Maps for Feature Extraction
    Deep Boltzmann Machines for Recommendation Systems
    Auto Encoders for Recommendation Systems

the neuron: input value1,2,3 → neuron--→output signal

 ANN library in r
 install.packages(h2o)
Convolutional neural networks CNN :
steps 
1)  convolution operation : edge, emboss, context, 
2) ReLU layer : black =negative, white = positive values, 
3) pooling: exp: cheetha, freature map-→ pooled feature mapping, evaluation of pooling operations in convolutional architectures for object recognition.
4) flattening
5) full connection
6) summary
extra :sofimax & cross entropy
input image-→convolution(convolution layer) -→pooling(pooling layer)-->flattening
input image * feature detector = feature map
convolution types 

DIMENSIONALITY REDUCTION TECHNIQUES IN ML R :

There are two types of techniques 
1.feature selection
2.feature extraction

Brief info :Feature Selection techniques are Backward Elimination, Forward Selection, Bidirectional Elimination, Score Comparison and more. These techniques in Regression.

there extraction technique :
  1. Principal Component Analysis (PCA)
       --noise filtering
       --visualization
       --feature extraction
       --stock market predictions
       --gene data analysis
        goal of pca : identify patterns in data and detect the correlation between variables.reduce dimentional dataset by projecting it on to a K-dimentional subspace (where K<D). we learn relationship between X and Y values.
  2. linear discriminant analysis (LDA) library (MASS)
        -- sounds similar to pca but
        --feature space and sub space
        --pca :component axes that maximize the variables
        --ida : maximizing the component axes for class-separation
        --from the n independent variables of your dataset. LDA extracts P<=N new independent variables that separate the most the classes of the depenendent variable.
  3.Kernal PCA
  
  4.Quadratic Discriminant analysis (QDA)
  
  
  MODEL SELECTION IN ML R
  
  1) k-fold cross validation in model selection :

    dataset -→training & test sets → 8th iterations

                The bias-variance trade off
                    1)  high bias low variance
                    2) high bias high variance
                    3) low bias low variance
                    4) low bias high variance
  2) grid search
  
  XG BOOST IN ML R library(caret) library(xgboost)
  
                  1)Importing the libraries
                  2)Importing the dataset
                  3)Splitting the dataset into the Training and Test set
                  4)fitting / Training XGBoost on the Training set                                           (classification) library(xgboost)
                  5)Making the confusion matrix
                  6)Applying k-fold Cross-Validation
  
  