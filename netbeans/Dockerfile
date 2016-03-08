FROM huggosantos/wildfly-mysql
MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com"

#RUN adduser --disabled-password --home /desenvolvedor --gecos "" desenvolvedor


USER root

#choose language fit ubuntu
#RUN locale-gen pt_BR.UTF-8 && update-locale LANG=pt_BR.UTF-8

#install git
RUN apt-get update && apt-get install -y  git 

#pull project SADE IFBA Eunapolis-BA 
RUN mkdir /home/NetBeansProjects 
RUN cd /home/NetBeansProjects &&  git clone https://github.com/IFBAEunapolis/SADE.git 

#install unzip
RUN sudo apt-get install unzip

#RUN sudo apt-get install wget

#install netbeans
RUN mkdir /home/netbeans-8.1
RUN cd /home/netbeans-8.1 && wget $download http://download.netbeans.org/netbeans/8.1/final/zip/moduleclusters/netbeans-8.1-201510222201-all-in-one.zip
RUN cd /home/netbeans-8.1 && unzip netbeans-8.1-201510222201-all-in-one.zip
RUN cd /home/netbeans-8.1/netbeans/bin/ && chmod +x netbeans

RUN chmod +x /home/netbeans-8.1/netbeans/bin/
CMD /home/netbeans-8.1/netbeans/bin/  && sh netbeans


#install maven
#RUN mkdir /usr/local/maven 
#RUN chmod 777 /usr/local/maven 
#RUN cd /usr/local/maven && curl -OL http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.tar.gz
#RUN sudo tar -zxf .semaphore-cache/apache-maven-3.3.3-bin.tar.gz -C /usr/local/maven
#RUN sudo ln -s /usr/local/maven/apache-maven-3.3.3/bin/mvn /usr/bin/mvn



