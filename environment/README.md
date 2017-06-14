# Environment Installation and Configuration

The experiments can be reproduced in three distinct manners: through anaconda installation on local so, through docker, and oracle virtual box. All of the options make use of Jupyter Notebook as their fundamental tool.

**It is advisable to use Docker as the most reliable of the three options, since image environment will be identical to when it was created. If you rather do it without docker, using only  your local SO and anaconda, be aware that other installations you have, such as other python versions, might affect reproducibility. Or if you prefer virtual box, be aware the file is around 4GB and download might  be affected due to internet limitations**
<br>
<br>
=======================================< **DOCKER** >======================================== 

### Steps to reproduce via DOCKER on WINDOWS
1. For most windows versions, install Docker Tool Box: https://www.docker.com/products/docker-toolbox. For Windows 10 Professional and Enterprise 64-bit: https://store.docker.com/editions/community/docker-ce-desktop-windows
2. Clone for first time or update local git repository. For docker to mount directory when running image, cloned directory must be inside C:\Users\\{user} directory.<br> Issue command: **git clone https://github.com/ecalio07/enron-paper.git**
3. Open Docker Terminal, make note docker terminal id. Usually it is (192.168.99.100)
4. Run the image: **docker run -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**<br>
This command will download image ecalio07/ia369z:4.0, if it is not local, copy all content from you local project directory to the docker container (/home/ds/notebooks) and run image in the container.<br> 
* Example with **Windows path**: **docker run -p 8888:8888 -v /c/Users/DELL/enron-paper:/home/ds/notebooks ecalio07/ia369z:4.0** 
5. Open browser, and use the terminal id from step 2, to compose the url: **http://192.168.99.100:8888** and paste it. 
6. Navigate to /deliver folder and run the most recent paper cells.

### Steps to reproduce via DOCKER on MAC
1. If you don´t have docker client, please install:
https://store.docker.com/editions/community/docker-ce-server-ubuntu
2. Clone for first time or update local git repository, preferably under /Users/{user}/ directory.<br> Issue command: **git clone https://github.com/ecalio07/enron-paper.git**
3. Run the image: **docker run -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**<br>
This command will download image ecalio07/ia369z:4.0, if it is not local, copy all content from you local project directory to the docker container (/home/ds/notebooks) and run image in the container.<br> 
**Example in MAC path: docker run -p 8888:8888 -v /Users/marie/enron-paper:/home/ds/notebooks ecalio07/ia369z:4.0**
4. Go to the browser and paste the following url: **http://localhost:8888**
5. In jupyter(browser), access file inside folder deliver and following instructions.

### Steps to reproduce via DOCKER on UBUNTU:
1. If you don´t have docker client, please install:
https://store.docker.com/editions/community/docker-ce-server-ubuntu
2. Clone for first time or update local git repository: git clone https://github.com/ecalio07/enron-paper.git
3. Download docker image. Enter command in terminal: **sudo docker pull ecalio07/ia369z:4.0**
4. Run image to create the container. Enter command: **sudo docker run -d -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**
5. Go to the browser and paste the following url: **http://localhost:8888**
6. In jupyter(browser), access file inside folder deliver and following instructions.


===================================< **LOCAL SO WITH ANACONDA** >============================ 

### Steps to reproduce via Anaconda on Windows:
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Enter into preferred directoy and issue the command to clone project:**git clone https://github.com/ecalio07/enron-paper.git**
4. Enter into the newly cloned directory root(c:\xxx\xxx\enron-paper) and issue the command: **jupyter notebook**
5. In the browser enter url http://localhost:8888 and reproduce the experiments using the most recent file .ipynb within /deliver directory

### Steps to reproduce via Anaconda on Ubuntu:
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Enter into preferred directoy and issue the command to clone project:**git clone https://github.com/ecalio07/enron-paper.git** 
4. Enter into the newly cloned directory root(/home/youruser/notebooks/enron-paper) and issue the command: **jupyter notebook** 
5. In the browser enter url http://localhost:8888 and reproduce the experiments using the most recent file .ipynb within /deliver directory

=======================================< **VIRTUALBOX** >===================================

### Steps to reproduce via VirtualBox:
1. If you don't have VirtualBox installed, please consult url:
https://www.virtualbox.org/wiki/Downloads
2. Start Oracle Virtual Machine and donwload the file .OVA [here](https://drive.google.com/file/d/0B4KJCoCOJkpGOEYwYWhPb18ySmM/view?usp=sharing)
3. Go to menu File/Import Appliance, and select donwloaded *.OVA.
4. Start  (VM Ubuntu 16.04_escience) and open a terminal.
5. Go into the directory enron-paper: **cd ~/notebooks/enron-paper**
6. Verify if git project is udated using (git fetch/git status). If necessary, update from repository.
7. Inside enron-paper root directory, execute the following command: **jupyter notebook**
8. Await for the browser to open in the following url : http://localhost:8888. Insert manually if necessary.
9. To reproduce the project, follow instructions in the most recent paper into /deliver folder.
 
