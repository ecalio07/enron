
# Fraud Detection Machine Learning on Enron Enteprise Dataset

This project contains files, based on the "Udacity - Introduction to Machine Leaning course", used for the subject course "IA369Z - Computational Reproducibility Research" at Unicamp - Professor Leticia Rittner, student Eduardo Calio.

This is being used for **educational pourposes only**.

## Introduction

The purpose of this project is to provide a **reproducible paper** regarding studies on how well Naive Bayes, SVM, and Decision Tree Machine Learning Algorithms can indentify emails by their authors using a pre-processed list of email texts and the corresponding authors based on the emails and authors dataset of the famous fraud scandal of the american bankrupt Enron Corporation. We will also study ways to work with parameters to improve accuracy and performance.

## Environment
Enviroment is essencially based on the following tools:
* Anaconda 4.3.1(Jupyter Notebook Server 4.3.1, Python 2.7.13, scikit-learn library version 0.18.1) and git version 2.7.4.
* Docker Client 17.03.1-ce
* Docker Image: ecalio07/ia369z:4.0 was adapted, due to incompatibility issues with the code, from original image dataquestio/python2-starter, in order to have all tools but more recent versions of the following libraries: scikit-learn from 0.17 to 0.18, nltk from 3.1 to 3.2.

For installation instructions and detailed reproduction steps, click [here](environment/README.md)<br>
For suggestions on best reproducibility practices, click [here](environment/BEST_PRACTICES.md)

## Structure

* /data: Holds the dataset files (email_authors.pkl and  word_data), preprocessed by Katie Malone for Udacity machine learning training course.

* /dev: In this directory it is available **.ipynb files** that are imported by the main file in deliver folder

* /deliver: Refer to the most recent **.ipynb** file in this folder as the main stable reproducible paper:<br>

* /figures: Contains image files imported and displayed by the main files.

## Workflow Experiments Overview: Inputs and Outputs

<img src="figures/workflow.png" />






