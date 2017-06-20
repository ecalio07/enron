
# BEST PRACTICES

If you intend to work with Machine Learning with focus on Reprodutibility, I advise the use of the following tools.

Among all the recommended tools below, my favorite option is to use Jupyter Notebook, python and scikit learn libray installed in a **Docker image**, such as dataquestio/python2-starter. In this work, I could experienced that the use of docker prevented many reprodutibility errors to happen in other machines that already had other python version installed or other tools versions. 
 
## Anaconda:
It is the Leading Open Data Science Platform . It comes with python, Jupyter Notebook, Spider other tools to make development easier. 

**Recomendations(Dos and Don'ts):**
* Do: Prefer installing Anaconda, whenever is possible, rather than installing each library individually, for this will prevent compatibility issues. 
* Do: Take advantage of sckitlearn libray. It has plenty of functionallities for Machine Learning operations.
 
## Jupyter Notebook:
Excellet tool for reprodutibility. It enable documents to contain both code and rich text elements.
Because of the mix of code and text elements, these documents are the ideal place to bring together an analysis description and its results as well as they can be executed perform the data analysis in real time.

**Recomendations(Dos and Don'ts):**
* Don´t: Mix text and code directly into your main notebook, it is better to keep notebooks with code in separted files to be imported into the main notebook by the use of **%run** command. This will import results from other notebooks without importing the code.
* Do: Think of import references path just like the terminal path structure. For instance, if you have your running document inside /deliver folder, and you want to import a image from /figures, you have to move one directory up **(../)** and then enter figures folder: "../figures".
* Don´t: chunk all your code in just one cell. It is better to have other cells to hold part of the code, like small modules. For it is easier to understand the code and make maintenances.
* Do: Prefer to **define functions in Jupyter files**, whenever is possible, instead of keeping them in python files for later add imports.
* Don´t: Initalize jupyter from double click on its icon and waist time trying to set up a initial directory for working project. It is simpler to start jupyter from terminal, by typing **"jupyter notebook"**, after entering the directory you wish. Notebook will consider the location you initialized the tool as the root of the project.
* Do: Prefer to have a markdown cell to highligh a portion of the code explanation, rather than having a big cell with a lot of comments. Long comments might not be noticed, for it can be boring to read.
* Do: Version Jupyter Notebook files using names directly and through git versioning to specifying changes in commit messages
* Do: Use directory organization: Data (for datasets), Deliver(notebooks to deliver), Dev(notebooks with codes to be imported by main notebook in /deliver folder), Figures (to hold images).

## Docker:
It is a container platform that can hold envornment installations. Images have much smaller sizes than a Virtual Machine and enables a reprodutible environment. It has become to me a essencial tool to work in conjuntion with Jupyter Notebook.

It is easy to hold and share, but complex at first steps for learning. 

**Recomendations(Dos and Don'ts):**
* Don´t: Use GitHub to keep docker images, use instead DockerHub.
* Do: Use (For Windows Environment) Docker Quickstart Terminal IP address to compose url when accessing Jupyter Notebook through browser. For instance: http://192.168.99.100:8888. Localhost + port number will not work, since it is like running on a new Machine. For other operational systems, like Linux and Mac, localhost will work just fine, for you won´t be using Docker QTerminal. 
* Don´t: Place (For Windows Environment) projects, to be accessed by Docker Terminal, outside C:\Users\{user} directory, otherwise mounting might not be possible. 
* Do: Use Long Container ID for creating a new image based on another through commit command. Changes might not be saved if used truncated container ID.

## VirtualBox (VM)
A very good Virtualization Tool. I is simple to use and reproduce, but file can become too big to hold and share.

**Recomendations(Dos and Don'ts):**
* Do: Install Operation Sytem as compact as possible, so as to reduce size of VM.
* Don´t: Install third party softwares when composing a Ubuntu virtual machine, it will generate a much larger file than necessary.

## Git (tool) and GitHub (repository):
Organized commits and the use branches, expecially if you have to do many changes in code. In my first code version, parameters tunning were manual. Then I made changes to use GridSearh and code stopped working because of sckitlearn version and other compatibility issues.
I should have created a new branch for big changes.

**Recomendations(Dos and Don'ts):**
* Do: Create a new branch when making huge changes of code, or changing core functionalities.
* Do: Each data scientists, when working in a team, has dev branch that they push to daily. Then, merge to master via pull request
* Don´t: Acumulate to many changes for one solo commit. For if you have to retroced the commit because of one small mistake, you will endup lossing all the other sucessful changes.
* Do: Commit meaninful messages to commit. It will be a precious remminder when looking at the history log.
