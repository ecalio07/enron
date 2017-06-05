## Environment Tools

This project is based on the following tools: git version 2.7.4, anaconda 4.3.1 (64-bit), Jupyter Notebook Server 4.3.1, Python 2.7.13, scikit-learn library. 

The experiments can be reproduced in three distinct manners: through anaconda installation, through docker and oracle virtual box. However, all of them make use of Jupyter Notebook as their fundamental tool.

# Environment Installation and Configuration

This project is based on the following tools: git version 2.7.4, anaconda 4.3.1 (64-bit), Jupyter Notebook Server 4.3.1, Python 2.7.13, scikit-learn library. 

The experiments can be reproduced in three distinct manners: through anaconda installation, through docker and oracle virtual box. However, all of them make use of Jupyter Notebook as their fundamental tool.

### Steps to reproduce via Anaconda:
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Create a new folder: **mkdir /home/youruser/notebooks**
4. Enter this new folder: **cd /home/youruser/notebooks** and issue the command: 
**git clone https://github.com/ecalio07/enron-paper.git**
5. Enter into the newly created directory: **cd /home/youruser/notebooks/enron-paper**.
6. Still in the direcotry from step 5, execute: **jupyter notebook**
7. Reproduce the experiments following .ipynb file within deliver directory

Obs: Para windows são os mesmos passos, mudando somente a estrutura de diretórios.


### Steps to reproduce via Docker (Ubuntu):
1. If you don´t have docker client, please install:
https://store.docker.com/editions/community/docker-ce-server-ubuntu
2. Donwload the image: **sudo docker pull dataquestio/python2-starter**
3. Run image to create the container: **docker run -d -p 8888:8888 -v /home/vik/notebooks:/home/ds/notebooks dataquestio/python2-starter**
4. Go into the following directory: **cd /home/vik/notebooks**
5. Clone the project from GitHub: **git clone https://github.com/ecalio07/enron-paper.git**
6. Copy files from /home/vik/notebooks/enron-paper (arquivos locais) to directory inside tocker /home/ds/notebooks. Isto pode ser feito de duas maneira:
6.1. Via  cp
6.2. Or through Jupyter localhost:8888 via browser, create folders (dev, deliver, figures, data) e and upload local files to (/home/vik/notebooks/enron-paper).
7. In jupyter(browser), access file inside folder deliver and following instructions.

 
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
