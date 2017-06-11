# Environment Installation and Configuration

This project is based on the following tools: git version 2.7.4, Anaconda 4.3.1 (64-bit), Jupyter Notebook Server 4.3.1, Python 2.7.13, scikit-learn library version 0.18.1. 

The experiments can be reproduced in three distinct manners: through anaconda installation on local so, through docker and oracle virtual box. However, all of them make use of Jupyter Notebook as their fundamental tool.

**It is advisable to use Docker as the most reliable of the three options, since image environment will be identical to when it was created. If you rather do it without docker, using only  your local SO and anaconda, be aware that other installations you have, such as other python versions, might affect reproducibility. Or if you prefer virtual box, be aware the file is around 4GB and download might  be affected due to internet limitations**

### Steps to reproduce via Docker on Windows:
1. For most windows versions, install Docker Tool Box: https://www.docker.com/products/docker-toolbox. For Windows 10 Professional or or Enterprise 64-bit: https://store.docker.com/editions/community/docker-ce-desktop-windows
2. Clone for first time or update local git repository. **Note: For docker to see this directory, it must be inside C:\Users\\{user} directory:**git clone https://github.com/ecalio07/enron-paper.git
3. Open Docker Terminal, make note docker terminal id. Usually it is (192.168.99.100)
4. Enter command: **docker pull ecalio07/ia369z:4.0**
5. Run the image: **docker run -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**. This command will copy all content from you local project directory to the docker container (/home/ds/notebooks). 
Example with windows path: **docker run -p 8888:8888 -v /c/Users/DELL/enron-paper:/home/ds/notebooks ecalio07/ia369z:4.0** 
6. Open browser, and use the terminal id from step 2, to compose the url: **http://192.168.99.100:8888** and paste it.
7. Navigate to /deliver folder and run the most recent paper cells.

### Steps to reproduce via Docker on Ubuntu:
1. If you don´t have docker client, please install:
https://store.docker.com/editions/community/docker-ce-server-ubuntu
2. Clone for first time or update local git repository: git clone https://github.com/ecalio07/enron-paper.git
3. Download docker image. Enter command in terminal: **sudo docker pull ecalio07/ia369z:4.0**
4. Run image to create the container. Enter command: **sudo docker run -d -p 8888:8888 -v \<cloned enron-paper directory>\:/home/ds/notebooks ecalio07/ia369z:4.0**
5. Go to the browser and paste the following url: **http://localhost:8888**
6. In jupyter(browser), access file inside folder deliver and following instructions.

### Steps to reproduce via Anaconda on Windows (using terminal):
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Enter into preferred directoy and issue the command to clone project:**git clone https://github.com/ecalio07/enron-paper.git**
4. Enter into the newly cloned directory root(c:\xxx\xxx\enron-paper) and issue the command: **jupyter notebook**
5. In the browser enter url http://localhost:8888 and reproduce the experiments using the most recent file .ipynb within /deliver directory

### Steps to reproduce via Anaconda on Ubuntu (using terminal):
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Enter into preferred directoy and issue the command to clone project:**git clone https://github.com/ecalio07/enron-paper.git** 
4. Enter into the newly cloned directory root(/home/youruser/notebooks/enron-paper) and issue the command: **jupyter notebook** 
5. Still in the direcotry from step 5, execute: **jupyter notebook**
6. In the browser enter url http://localhost:8888 and reproduce the experiments using the most recent file .ipynb within /deliver directory
 
### Steps to reproduce via VirtualBox:
1. If you don't have VirtualBox installed, please consult url:
https://www.virtualbox.org/wiki/Downloads
2. Start Oracle Virtual Machine and donwload the file .OVA [aqui](https://drive.google.com/file/d/0B4KJCoCOJkpGOEYwYWhPb18ySmM/view?usp=sharing)
3. go to menu File/Import Appliance, and select donwloaded *.OVA.
4. start  (VM Ubuntu 16.04_escience) and open a terminal.
5. Go into the directory enron-paper: **cd ~/notebooks/enron-paper**
6. Verify if the project is updated:
6.1. **sudo git fetch**
6.2. **sudo git status**
6.3. (options) if not updated : **sudo git pull**
7. Inside enron-paper, execute the following command:
7.1 **jupyter notebook**
8. Await for the browser to open in the following url : http://localhost:8888. Inser manually if necessary.
9. To reproduce the project, following instruction in the most recent paper in deliver folder.
