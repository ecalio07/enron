
# Fraud detection Machine Learning on Enron Enteprise Dataset

## Introduction

The purpose of this project is to provide a **reproducible paper** regarding studies on how well Naive Bayes, SVM, and Decision Tree machine learning algorithms can indentify emails by their authors using a pre-processed list of email texts and the corresponding authors based on the text dataset(comprised of 146 users with 21 features each) of the famous fraud scandal of the american bankrupt Enron Corporation.

## Reprodutibility
This project can be reproduced in two distinct manners:

### 1. Jupyter Notebook tool
By following instructions in the file contained in the **deliver**, you will be able to setup the proper environment on your local machine, and install and use Jupyter Notebook as your main tool.

### 2. Docker tool
By following instructions in the file contained in the **deliver**, you will be able to install docker client tool, and make use of the docker file available in the **environments** folder. When running the experiment, you will still be using Jupyter Notebook as the main tool, however, the difference now is that you won't have to install python, java, and jupyter notebook, for they will be embeded in the docker file and be ready to use.

**NB:** All contents used for this paper where based on the **"Udacity - Introduction to Machine Leaning course"**, and it is being used for educational pourposes only.


## Structure and Files

Directories and Files explanation:

**Data:** The dataset files are named **email_authors.pkl** and **word_data** which has been developed by Katie Malone for Udacity machine learning training course.

**Dev:** In this directory you made available minor releases of our reproducible papers using jupyter notebook. Code scripts and text procedures are embeded in the ipynb files. Please, note that this has been made available only to display the evolution of the project. For the most stable verstion, please refer to files contained in the **Deliver** folder.

**Deliver:** Contains the stable reproducible papers.

**Environment:** Contains DOCKER version, an alternative way to reproduce the experiments without having to set up installation of tools by yourself. 

**Figures:** Contains image files imported and displayed by the main files.

To reproduce this experiment, you will find the main file (last version of .ypnp) in this folder . The delivery file will contain all instructions, and it will be regarded as our reproducible paper. By papaer I mean not only the text, but data, code, and all resources required to make the experiments reproducible. 

**Tools:** Contains the auxiliary commom .py files imported by main scripts embeded in the papers.

<img src="structure.png" />




