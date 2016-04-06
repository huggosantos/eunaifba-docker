FROM huggosantos/wildfly

MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com" 
USER root 

RUN apt-get update && apt-get install -q -y xorg git unzip axel 

RUN axel http://download.netbeans.org/netbeans/8.1/final/zip/moduleclusters/netbeans-8.1-201510222201-all-in-one.zip
RUN unzip netbeans-8.1-201510222201-all-in-one.zip

CMD /opt/jboss/netbeans/bin/netbeans
