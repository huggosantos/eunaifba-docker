
FROM ubuntu:15.10
MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com"

#install git
RUN apt-get update && apt-get install -y  git 
#RUN mkdir /root/NetBeansProjects/ git clone https://github.com/IFBAEunapolis/SADE.git       

RUN apt-get purge ^openjdk-6-*
#java 8
RUN apt-get install software-properties-common -y
RUN add-apt-repository ppa:webupd8team/java -y
RUN apt-get update
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections
RUN apt-get install oracle-java8-installer -y
RUN apt-get install oracle-java8-set-default

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

ENV TMP_DOWNLOAD /tmp/downloads
RUN mkdir -p ${TMP_DOWNLOAD}
WORKDIR ${TMP_DOWNLOAD}

#install netbeans
RUN wget -vP $TMP_DOWNLOAD http://download.netbeans.org/netbeans/8.1/final/bundles/netbeans-8.1-linux.sh
ENV NETBEANS_SCRIPT=$TMP_DOWNLOAD/netbeans-8.1-linux.sh
RUN chmod +x $NETBEANS_SCRIPT   
RUN apt-get install -y  libxext-dev libxrender-dev libxtst-dev && apt-get clean && rm -rf /var/lib/apt/lists/*   
RUN $NETBEANS_SCRIPT --silent -J-Djava.awt.headless=true -J-Dswing.defaultlaf=javax.swing.plaf.nimbus.NimbusLookAndFeel
RUN sed -e '/netbeans_jdkhome/ s/^#*/#/' -i /usr/local/netbeans-8.1/etc/netbeans.conf

CMD /usr/local/netbeans-8.1/bin/netbeans --laf com.sun.java.swing.plaf.nimbus.NimbusLookAndFeel

RUN locale-gen pt_BR.UTF-8 && update-locale LANG=pt_BR.UTF-8

#pull project SADE IFBA Eunapolis-BA 
RUN mkdir /root/NetBeansProjects 
RUN cd /root/NetBeansProjects &&  git clone https://github.com/IFBAEunapolis/SADE.git 
  
#install maven
#RUN mkdir /usr/local/maven 
#RUN chmod 777 /usr/local/maven 
#RUN cd /usr/local/maven && curl -OL http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.tar.gz
#RUN sudo tar -zxf .semaphore-cache/apache-maven-3.3.3-bin.tar.gz -C /usr/local/maven
#RUN sudo ln -s /usr/local/maven/apache-maven-3.3.3/bin/mvn /usr/bin/mvn
#RUN mvn -v 
