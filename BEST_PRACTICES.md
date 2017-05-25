
# DIÁRIO BEST PRACTICE
 
Neste diário, existem **3 possibilidades distintas de reprodução** dos experimentos.
 
Também consta dificuldades encontradas, recomendações e passos que podem ser úteis para um projeto de reprodutibilidade similar a este.


## 1 - REPRODUÇÃO NO UBUNTU/WINDOWS VIA ANACONDA:
 
### Observações:
No início comecei instalando cada ferramenta individualmente (git, python, jupyter) mas depois cheguei a conclusão que é perda de tempo. Salvo casos mais específicos, eu  indico a instalação direta do Anaconda, que contém todas as ferramentas necessárias neste projeto, inclusive a biblioteca scikit-learn. 
 
### Passos para reproduzir o experimento:
1. Download and Install Anaconda 4.3.1 for Python 2.7.13. https://www.continuum.io/downloads . Anaconda will include all packages necessary for this experiment: git, python 2.7, scikit-learn and jupyter notebook.
2. After installation close the terminal and start a new one.
3. Create a new folder: **mkdir /home/youruser/notebooks**
4. Enter this new folder: **cd /home/youruser/notebooks** and issue the command: 
**git clone https://github.com/ecalio07/enron-paper.git**
5. Enter into the newly created directory: **cd /home/youruser/notebooks/enron-paper**.
6. Still in the direcotry from step 5, execute: **jupyter notebook**
7. Reproduce the experiments following .ipynb file within deliver directory

## 2 - REPRODUÇÃO NO WINDOWS/UBUNTU VIA VIRTUALBOX:
 
### Observações:
Encontrei vários erros de compatibilidade e perdi muito tempo tentando reproduzir o experimento via Docker no Windows. Sendo assim, a maneira mais eficaz foi criar uma Virtual Machine com SO Ubuntu, mas criada contemplando os exatos procedimentos de instalação da sessão “1.) Reprodução no Ubuntu/Windows via Anaconda”. Contudo, antes de começar os testes, verifique se os arquivos locais da VM estão atualizados com o repositório git.
 
### Passos para reproduzir o experimento:
1. Caso não possua a instalação do VirtualBox, favor instale conforme url:
https://www.virtualbox.org/wiki/Downloads
2. Inicialize o Oracle Virtual Machine e no meu Arquivo/Importar Appliance, selecione o arquivo com extensão *.OVA (contido na pasta environments do projeto).
3. Execute a VM importada (VM Ubuntu 16.04_escience) e abra um terminal de linha de commando.
4. Entre no diretorio principal: **cd ~/notebooks/enron-paper**
5. Verifique se projeto está atualizado:
5.1. **sudo git fetch**
5.2. **sudo git status**
5.3. (opcional) caso esteja desatualizado : **sudo git pull**
6. Estando ainda dentro do diretório enron-paper, execute o comando:
6.1 **jupyter notebook**
7. Aguarde o browser abrir automaticamente na url : http://localhost:8888. Caso isso não ocorra, insira a url manualmente no browser.
8. Para reproduzir o projeto, execute as instruções do paper contido dentro da pasta deliver.
 
Assim, basta ter o VirtualBox 5.0 ou superior instalado no Windows, ou até mesmo em uma outra máquina Linux, e importar o arquivo “VM-Ubutu14.04_escience.ova” para então rodar e reproduzir o experimento, bastando apenas seguir a partir do passo 4 da sessão 1.

## 3 - REPRODUÇÃO NO UBUNTU VIA DOCKER:
 
### Observações:
Para não iniciar instalação do ambiente reprodutível do zero, tendo que criar uma imagem e instalar cada ferramenta individualmente, aconselho a instalação do docker cliente e em seguida fazer o pull da imagem dataquestio/python2-starter, pois ela já contempla todo o ambiente integrado do anaconda. 
 
Sendo assim, baixei a imagem dataquestio/python2-starter, iniciei o notebook e montei a estrutura do github. O projeto funcionou perfeitamente. Então, fiz o commit com um novo nome e push para minha conta no Docker Hub.
 
O teste da reprodutibilidade foi instalar somente o docker em uma máquina ubuntu que não tivesse nenhuma outra ferramenta e-science. Assim, baixei a imagem do Docker Hub e inicializei o notebook. Mas para minha surpresa, ele não continha nenhum dos dados que eu havia acrescentado. Acredito que meu erro foi não ter entendido que ele salva na imagem as instalações e configurações, mas não tais tipos de dados.
 
Conclui então que como a diferença da imagem original para a que eu havia alterado era apenas os dados (.ipynb, py files), resolvi não mais criar imagem nova e armazená-la no Docker Hub, mas simplesmente utilizar a imagem já existente juntamente com os dados do meu projeto clonados do GitHub. 
 
### Passos para reproduzir o experimento:
1. If you don´t have docker client, please install:
https://store.docker.com/editions/community/docker-ce-server-ubuntu
2. Baixe a imagem pública: **sudo docker pull dataquestio/python2-starter**
3. Rode a imagem para criar o container: **docker run -d -p 8888:8888 -v /home/vik/notebooks:/home/ds/notebooks dataquestio/python2-starter**
4. Enter into the following directory: **cd /home/vik/notebooks**
5. Clone the project from GitHub: **git clone https://github.com/ecalio07/enron-paper.git**
6. Agora, os arquivos precisam ser copiados do diretório /home/vik/notebooks/enron-paper (arquivos locais) para o diretório dentro do docker /home/ds/notebooks. Isto pode ser feito de duas maneira:
6.1. Via comando cp
6.2. Ou acessando o jupyter localhost:8888 via browser, criando pastas(dev, deliver, figures, tools, data) e fazendo o upload dos arquivos locais(/home/vik/notebooks/enron-paper).
7. Agora, jupyter no browser, basta acessar o arquivo contido na pasta deliver e seguir as instruções do paper.


## OBSERVAÇÕES SOBRE JUPYTER NOTEBOOK
 
No início tive algumas dificuldades para trabalhar com a parte textual do notebook. Depois descobri que é na verdade simples, bastando apenas utilizar a célula como tipo markdown para inserir textos.
 
Perdi certo tempo também insistindo em configurar um diretório padrão para inicializar o notebook via parte gráfica, ao clicar no ícone de inicialização. Apareciam pasta e arquivos indesejados e tentei sem sucesso fixar um diretório de abertura padrão. Depois descobri que é muito mais simples inicializar o notebook por linha de comando partindo da pasta desejada. Assim, se quero que somente as pastas do meu projeto clonado do gitHub apareçam na raiz do notebook no browser, basta entrar na pasta desejada e chamar o notebook. Ex:
cd C:\Users\DELL\Projetos\enron-paper
C:\Users\DELL\Projetos\enron-paper> jupyter notebook


 
## CONCLUSÃO 
 
Acredito que as opções 1 e 2 de reprodutibilidade aqui apresentadas são as mais convenientes para um projeto similar a este. Tanto para quem escreve o projeto, quanto quem somente reproduz. Talvez pela pouca experiência com o docker ou pela complexidade acrescentada, achei a opção 3 menos favorável.
 
Recomendo o uso do Anaconda, por disponibilizar o python, Jupyter Notebook, git, Spider e outros, tudo através de uma instalação simples e com ferramentas poderosas.
 
O Jupyter Notebook atendeu muito bem as expectativas.


## REFERÊNCIAS
**????**



