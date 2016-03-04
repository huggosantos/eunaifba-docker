FROM huggosantos/wildfly-mysql
MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com"

#RUN adduser --disabled-password --home /desevolvedor --gecos "" desevolvedor

#USER desenvolvedor


#choose language fit ubuntu
#RUN locale-gen pt_BR.UTF-8 && update-locale LANG=pt_BR.UTF-8

#install git
RUN apt-get update && apt-get install -y  git 

#install netbeans
RUN download /home/netbeans-8.1
RUN wget $download http://download.netbeans.org/netbeans/8.1/final/zip/moduleclusters/netbeans-8.1-201510222201-all-in-one.zip
RUN cd /home/netbeans-8.1 && gunzip netbeans-8.1-201510222201-all-in-one.zip


#push project SADE IFBA Eunapolis-BA 
RUN mkdir /home/desenvovedor/NetBeansProjects 
RUN cd /home/desenvovedor/NetBeansProjects &&  git clone https://github.com/IFBAEunapolis/SADE.git 
   
#install maven
#RUN mkdir /usr/local/maven 
#RUN chmod 777 /usr/local/maven 
#RUN cd /usr/local/maven && curl -OL http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.tar.gz
#RUN sudo tar -zxf .semaphore-cache/apache-maven-3.3.3-bin.tar.gz -C /usr/local/maven
#RUN sudo ln -s /usr/local/maven/apache-maven-3.3.3/bin/mvn /usr/bin/mvn
