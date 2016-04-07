[![Stories in Ready](https://badge.waffle.io/huggosantos/eunaifba-docker.png?label=ready&title=Ready)](https://waffle.io/huggosantos/eunaifba-docker)

[![Stories in Progress](https://badge.waffle.io/huggosantos/eunaifba-docker.png?label=in%20progress&title=In%20Progress)](https://waffle.io/huggosantos/eunaifba-docker/)

[![Docker Pulls](https://img.shields.io/docker/pulls/huggosantos/netbeans.svg?style=flat-square)](https://links.huggosantos/netbeans)



# Netbeans 8.1

Nesse repositório está presente o Dockerfile para construção da imagem do netbenas já com  wildfly 10.0.0, jdk 8, e o firefox 45 instalados para facilitar no desenvolvimento do projeto. Essa imagem do netbeans está baseada no sistema operecional linux, mas precisamente o ubuntu 14.04 lts. Depois do download da imagem feito nosse site -->  https://hub.docker.com/r/ifbaeunapolis/netbeans-wildfly-mysql-driver/ , pode-se criar o container dessa imagem através dos comandos abaixo.

### Pull da imagem no Docker Hub
```
docker pull huggosantos/netbeans
```
 

## RUN linux

Rodar esse comando primeiro caso a distribuição seja ubuntu. 
```
xhost +local:docker
```

### Run image
```
 sudo docker run -it --env="DISPLAY" --workdir="/home/$USER" --volume="/home/$USER:/home/$USER" --volume="/etc/group:/etc/group:ro" --volume="/etc/passwd:/etc/passwd:ro" --volume="/etc/shadow:/etc/shadow:ro" --volume="/etc/sudoers.d:/etc/sudoers.d:ro" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" --name netbeans huggosantos/netbeans
```

# RUN docker-compose

Caso for rodar via docker-compose, no repositorio já está incluso dois arquivos .yml, um para usarios linux, e outro para usuarios windows.
 
 No terminal  basta rodar o comando: 
```
 docker-compose -f netbeans-docker-compose.yml up
```
 Isso no diretorio onde estar o arquivo .yml .
 



 
