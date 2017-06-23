
# BEST PRACTICES

Reprodutibility recommendations found in this diary apply mostly to a scenario based on Machine Learning Classifiers working with a text dataset as input, and text and graph as output. Depending on your work's requirement, you might need to work with other programming languages and tools.

With regards to reproduciple papers, we should always have in mind that key words like data source format, data souce holding place, data source access, text, programming, images and environment, are crucial aspects to the success.

I would summarize sugestions in this diary as the following High Level Steps:

1 - Find first a **Literate Programming Tool** (plataform) that works with your required data, coding language, text, pictures.<br>
2 - Make use of **version control tool** like git, and a **repository** such as GitHub or Bitbucket, for these will be needed to version and share your work.<br>
3 - In addition to the tools and sharing reproducible components (code, paper, data), you must also **share(guarantee) the reproducible environment**. Docker is a great tool for that, or a hypervisor tool for **Virtual Machines**. <br>

**Obs: Without a container or virtualization, there's no way to "guarantee" reproduction on different environments. However, this word(guarantee) is too strong, because it is not possible to ensure a 100% success, since software also depend of hardware and local memory.**

Tests were made, without containers, and paper failed to reproduce in a machine where other previous dependencies were already installed such as more than one python versions.

For other instructions and detailed reproduction steps, click [here](../environment/README.md)<br> 


## 1 - Jupyter Notebook:

It is an excellet tool for reprodutibility. It enables documents to contain both code and rich text elements. And because of the mix of codes and text, these documents are the ideal place to bring together an analysis description and its results as well as they can be executed perform the data analysis in real time.

When I fist started this work, I intended to work with Python Programming language and scikit-learn library, because both are simple and very powerful for working with Data Science. I also required a platform that enabled working with a text dataset. 

I choose Jupyter over other reprodutibility tools for the all reasons already mentioned and the ones below:
* it has a strong community and great documentation;
* its flexibility  to work with many programming languages;
* it is simple and intuitive;
* enables working with source data, figures, text and code.

In summary, I recomend starting by deciding if programing language and datasource maches your literate programming choice.

**Dos and Don'ts when working with this tool:**
* Don´t: Mix text and code directly into your main notebook, it is better to keep notebooks with code in separted files to be imported into the main notebook by the use of **%run** command. This will import results from other notebooks without importing the code.
* Do: Think of import references path just like the terminal path structure. For instance, if you have your running document inside /deliver folder, and you want to import a image from /figures, you have to move one directory up **(../)** and then enter figures folder: "../figures".
* Don´t: chunk all your code in just one cell. It is better to have other cells to hold part of the code, like small modules. For it is easier to understand the code and make maintenances.
* Do: Prefer to **define functions in Jupyter files**, whenever is possible, instead of keeping them in python files for later add imports.
* Don´t: Initalize jupyter from double click on its icon and waist time trying to set up a initial directory for working project. It is simpler to start jupyter from terminal, by typing **"jupyter notebook"**, after entering the directory you wish. Notebook will consider the location you initialized the tool as the root of the project.
* Do: Prefer to have a markdown cell to highligh a portion of the code explanation, rather than having a big cell with a lot of comments. Long comments might not be noticed, for it can be boring to read.
* Do: Version Jupyter Notebook files using names directly and through git versioning to specifying changes in commit messages
* Do: Use directory organization: Data (for datasets), Deliver(notebooks to deliver), Dev(notebooks with codes to be imported by main notebook in /deliver folder), Figures (to hold images).

**Observation:** No Worflow Managing Tools was integrated with Jupyter Notebook, since it wasn't necessary for completing the work and it would much increase complexity.

 
## 2 - Git (tool) and GitHub (repository):

Organized commits and the use branches, expecially if you have to do many changes in code. In my first code version, parameters tunning were manual. Then I made changes to use GridSearh and code stopped working because of sckitlearn version and other compatibility issues.

I should have created a new branch for big changes.

**Dos and Don'ts when working with this tool:**
* Do: Create a new branch when making huge changes of code, or changing core functionalities.
* Do: Each data scientists, when working in a team, has dev branch that they push to daily. Then, merge to master via pull request
* Don´t: Acumulate to many changes for one solo commit. For if you have to retroced the commit because of one small mistake, you will endup lossing all the other sucessful changes.
* Do: Commit meaninful messages to commit. It will be a precious remminder when looking at the history log.

**Observation:** Basic commands were simple to use and met all needs.

## 3a - Docker:

It is a container platform that can hold envornment installations. Images have much smaller sizes than a Virtual Machine and enables a reprodutible environment. It has become to me a essencial tool to work in conjuntion with Jupyter Notebook.

It is easy to hold and share, but complex at first steps for learning. 

**Dos and Don'ts when working with this tool:**
* Don´t: Use GitHub to keep docker images, use instead DockerHub.
* Do: Use (For Windows Environment) Docker Quickstart Terminal IP address to compose url when accessing Jupyter Notebook through browser. For instance: http://192.168.99.100:8888. Localhost + port number will not work, since it is like running on a new Machine. For other operational systems, like Linux and Mac, localhost will work just fine, for you won´t be using Docker QTerminal. 
* Don´t: Place (For Windows Environment) projects, to be accessed by Docker Terminal, outside C:\Users\{user} directory, otherwise mounting might not be possible. 
* Do: Use Long Container ID for creating a new image based on another through commit command. Changes might not be saved if used truncated container ID.

**Observation:** This paper was reproduced in three diferent SOs through Docker: Windows, MAC OS, Linux.

## 3b - VirtualBox (VM)

A very good Virtualization Tool. I is simple to use and reproduce, but file can become too big to hold and share.

**Dos and Don'ts when working with this tool:**
* Do: Install Operation Sytem as compact as possible, so as to reduce size of VM.
* Don´t: Install third party softwares when composing a Ubuntu virtual machine, it will generate a much larger file than necessary.

**Observation:** This paper was not reproduced with this option due to bandwith limitations. In additon, because of the large size of the file, it can become a problem to store the file.

## References:

**Jupyter Notebook:** http://jupyter.org/ <br>
**Jupyter Notebook Guide:https:** http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/ <br>
**Docker:** http://training.play-with-docker.com/ <br>
**Git & GitHub Udacity course:** https://br.udacity.com/course/how-to-use-git-and-github--ud775/ <br>
**Git Documentation:** https://git-scm.com/documentation <br>
**Virtual Box Best Practices:** http://www.techrepublic.com/blog/10-things/10-ways-to-get-the-most-from-virtualbox/ <br>
