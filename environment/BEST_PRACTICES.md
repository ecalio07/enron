
# DIÁRIO BEST PRACTICE
 
### Anaconda:
No início comecei instalando cada ferramenta individualmente (git, python, jupyter) mas tive problemas de compatibilidade de versãoes com scikit-learn e outras bibliotecas. Aconselho a instalaçao do Anaconda diratemente. 
Recomendo o uso do Anaconda, por disponibilizar o python, Jupyter Notebook, git, Spider e outros, tudo através de uma instalação simples e com ferramentas poderosas.

 
### Jupyter Notebook:
Excellente ferramenta para reprodutibilidade.
No início tive algumas dificuldades para trabalhar com a parte textual do notebook. Depois descobri que é na verdade simples, bastando apenas utilizar a célula como tipo markdown para inserir textos.
 
Perdi certo tempo também insistindo em configurar um diretório padrão para inicializar o notebook via parte gráfica, ao clicar no ícone de inicialização. Apareciam pasta e arquivos indesejados e tentei sem sucesso fixar um diretório de abertura padrão. Depois descobri que é muito mais simples inicializar o notebook por linha de comando partindo da pasta desejada. Assim, se quero que somente as pastas do meu projeto clonado do gitHub apareçam na raiz do notebook no browser, basta entrar na pasta desejada e chamar o notebook. Ex:
cd C:\Users\DELL\Projetos\enron-paper
C:\Users\DELL\Projetos\enron-paper> jupyter notebook


### Docker:
Exige uma curva de aprendizado, mas garante a reprodutibilidade. Execente para trabalhar em conjunto com o Jupyter.
Aconselho o uso de uma imagem que já possue o anaconda instalado: dataquestio/python2-starter
Utilização do Docker Hub como repositório de imagens. Conclui então que como a diferença da imagem original para a que eu havia alterado era apenas os dados (.ipynb, py files), resolvi não mais criar imagem nova e armazená-la no Docker Hub, mas simplesmente utilizar a imagem já existente juntamente com os dados do meu projeto clonados do GitHub.

### VirtualBox (VM)
Simples e muito bom para garantir reprodutibilidade. Porém, esta opção talvez não seja a melhor, justamente pelo tamanho do arquivo. Por ter mais de 3GB, ficou inviável armazená-lo no GitHub.Tive que utilizar o Google Drive, que embora me permita compartilhar a pasta, está atrelado a uma conta particular.
