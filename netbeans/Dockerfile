FROM huggosantos/jdk8
MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com"

USER root


#choose language fit ubuntu
RUN locale-gen pt_BR.UTF-8 && update-locale LANG=pt_BR.UTF-8

#install git
RUN apt-get update && apt-get install -y  git 

#instal maven
RUN apt-get install -y maven 

#pull project SADE IFBA Eunapolis-BA 
#RUN mkdir /home/NetBeansProjects 
#RUN cd /home/NetBeansProjects &&  git clone https://github.com/IFBAEunapolis/SADE.git 

#instal unzip && axel && x11 serve Installation
RUN apt-get install unzip
RUN apt-get install -q -y axel 
RUN apt-get update 
RUN apt-get -y install xorg openbox
#install netbeans
RUN axel http://download.netbeans.org/netbeans/8.1/final/zip/moduleclusters/netbeans-8.1-201510222201-all-in-one.zip
RUN unzip netbeans-8.1-201510222201-all-in-one.zip


CMD /netbeans/bin/netbeans
