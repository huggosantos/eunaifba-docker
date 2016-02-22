FROM maven:3.3.3-jdk-8
MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com"

RUN wget http://download.netbeans.org/netbeans/8.1/final/bundles/netbeans-8.1-linux.sh -O /tmp/netbeans.sh -q && \
    chmod +x /tmp/netbeans.sh && \
    echo 'Installing netbeans' && \
    /tmp/netbeans.sh --silent --state /tmp/state.xml && \
    rm -rf /tmp/*
ADD run /usr/local/bin/netbeans
CMD /usr/local/bin/netbeans
