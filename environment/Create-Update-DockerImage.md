
# Image creation based on another:dataquestio/python2-starter

### Steps:

1. Go to Docker Hub and create an account and a new repository: https://hub.docker.com/
2. Make note of username and repository name. They will be used to create new image name: username/repositoryname. 
Ex: ecalio07/ia369z. There's no need to specify the tag, ex (:4.0).
3. Open docker terminal and issue command: **docker pull dataquestio/python2-starter** //This will donwload a pre-existent image from docker hub
4. Issue command: **docker run -p 8888:8888 -v \<git cloned diretory path\>:/home/ds/notebooks dataquestio/python2-starter**
5. Type the following command to print the long container id that is running. Only with this long id generation of 
new image works properly: **docker ps --no-trunc -q**
6. Make not of the long container id.
7. Enter docker prompt editor: **docker exec -it \<container id\> bash**
8. Make your personal installations or updates like: **pip install -U scikit-learn**, etc.
9. Exit image prompt: **Ctrl+p ctrl+q**
10. Container should still be running. Verify it with: **docker ps**
11. Generate new image from the running updated container: **docker commit \<longID\> \<new-image-name\>**.<br>
Example: **docker commit eee576806d5bb1500154a712867f7f2004e5fcc10a4c9e76806f4e6122c9ae76 ecalio07/ia369z:4.0**
12. Verify new image was correctly created: **docker images**
13. Stop the running container: **docker stop \<containerID\>**
14. Run newly created image:<br>
**docker run -p 8888:8888 -v \<git cloned diretory path\>:/home/ds/notebooks \<new-image-name\>**
15. Verify through browser it is working(docker terminal ip address + port number): **http://192.168.99.100:8888**
16. Login into Docker Hub: **docker login --username=\<yourdockerhubuser\> --email=\<emaildockerhub\>**
17. Upload image to Docker Hub: **docker push \<new-image-name\>**
18. Go to docker hub repository and verify on TAG tab that image was uploaded successfully.
