
# DIÁRIO BEST PRACTICE
 
## Anaconda:
No início comecei instalando cada ferramenta individualmente (git, python, jupyter) mas tive problemas de compatibilidade de versãoes com scikit-learn e outras bibliotecas. Aconselho a instalaçao do Anaconda diratemente. 
Recomendo o uso do Anaconda, por disponibilizar o python, Jupyter Notebook, git, Spider e outros, tudo através de uma instalação simples e com ferramentas poderosas.

**Recomendations(Dos and Don'ts):**
* Do: Prefer installing Anaconda, whenever is possible, rather than installing each library individually, for this will prevent compatibility issues. 

 
## Jupyter Notebook:
Excellet tool for reprodutibility. It enable documents to contain both code and rich text elements.
Because of the mix of code and text elements, these documents are the ideal place to bring together an analysis description and its results as well as they can be executed perform the data analysis in real time.

**Recomendations(Dos and Don'ts):**
* Don´t: Mix code and writing directly in you main notebook, it is better to keep notebook codes in separted files to be imported in main notebook by the use of **%run** command. This will import results from other notebooks without importing the code.
* Do: Think of import references path just like the terminal path structure. For instance, if you have your running document inside /deliver folder, and you want to import a image from /figures, you have to move one directory up **(../)** and then enter figures folder: "../figures"
* Don´t: chunk all your code in just one cell. It is better to use other cells split per modules. It is easier to understand the code.
* Do: Prefer to **define functions in Jupyter files**, whenever is possible, instead of keeping them in python files for later add imports.
* Don´t: Initalize jupyter from double click on its icon and waist time trying to set up a initial directory for working project. It is simpler to start jupyter from terminal, by typing **"jupyter notebook"**, after entering the directory you wish. Notebook will consider the location you initialized the tool as the root of the project.
* Do: Prefer to have a markdown cell to highligh a portion of the code explanation, rather than having a big cell with a lot of comments. Long comments might not be noticed, for it can be boring to read.
* Do: Version Jupyter Notebook files using names directly and through git versioning to specifying changes in commit messages
* Do: Use directory organization: Data (for datasets), Deliver(notebooks to deliver), Dev(notebooks with codes to be imported by main notebook in /deliver folder), Figures (to hold images).


## Docker:
Exige uma curva de aprendizado, mas garante a reprodutibilidade. Execente para trabalhar em conjunto com o Jupyter.
Used image with python, jupyter, skitlearn installed: dataquestio/python2-starter

Utilização do Docker Hub como repositório de imagens. Conclui então que como a diferença da imagem original para a que eu havia alterado era apenas os dados (.ipynb, py files), resolvi não mais criar imagem nova e armazená-la no Docker Hub, mas simplesmente utilizar a imagem já existente juntamente com os dados do meu projeto clonados do GitHub.
Pickle security issue problem on docker in windows.

**Recomendations(Dos and Don'ts):**
* Don´t: Use GitHub to keep docker images, use instead DockerHub.
* Do: Use (For Windows Environment) Docker Quickstart Terminal IP address to compose url when accessing Jupyter Notebook through browser. For instance: http://192.168.99.100:8888. Localhost + port number will not work, since it is like running on a new Machine. For other operational systems, like Linux and Mac, localhost will work just fine, for you won´t be using Docker QTerminal. 
* Don´t: Place (For Windows Environment) projects, to be accessed by Docker Terminal, outside C:\Users\{user} directory, otherwise mounting might not be possible. 
* Do: Use Long Container ID for creating a new image based on another through commit command. Changes might not be saved if used truncated container ID.


## VirtualBox (VM)
Simples e muito bom para garantir reprodutibilidade. Porém, esta opção talvez não seja a melhor, justamente pelo tamanho do arquivo. Por ter mais de 3GB, ficou inviável armazená-lo no GitHub.Tive que utilizar o Google Drive, que embora me permita compartilhar a pasta, está atrelado a uma conta particular.

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
