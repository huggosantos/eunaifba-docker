#
# NetBeans 8.1 + JDK 1.8u71 bundle
#
FROM huggosantos/ubuntu

MAINTAINER Huggo Oliveira "huggo.oliveira1@gmail.com"

# Install X11 tools and those needed here for downloads.
RUN apt-get update && apt-get install -y \ 
	curl libxext-dev libxrender-dev libxtst-dev unzip wget \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/* \
	&& rm -rf /tmp/*

# Alternative URL example
# NetBeans 8.0.2 + JDK 1.7u80
#ENV NETBEANS_URL=http://download.oracle.com/otn-pub/java/jdk-nb/7u80-8.0.2/jdk-7u80-nb-8_0_2-linux-x64.sh
#ENV POLICY_URL=http://download.oracle.com/otn-pub/java/jce/7/UnlimitedJCEPolicyJDK7.zip
ENV NETBEANS_URL=http://download.netbeans.org/netbeans/8.1/final/bundles/netbeans-8.1-javaee-linux.sh 
ENV POLICY_URL=http://download.oracle.com/otn-pub/java/jce/8/jce_policy-8.zip 
ENV COOKIE="Cookie: start.html?platform=linux&lang=pt_BR&option=javaee"

RUN wget --progress=bar:force $NETBEANS_URL -O /tmp/netbeans-8.1-javaee-linux.sh \
        --no-cookies --no-check-certificate --header "$COOKIE" \
        && echo "Installing NetBeans $NETBEANS_VERSION..." \
        && chmod +x /tmp/netbeans-8.1-javaee-linux.sh; sleep 1 \
        && /tmp/netbeans-8.1-javaee-linux.sh --silent \
        && rm -rf /tmp/* \
        && ln -s $(ls -d /usr/local/netbeans-*) /usr/local/netbeans

# Download & install the unlimited strength policy jars
RUN curl -L $POLICY_URL -o /tmp/policy.zip \
		--cookie 'oraclelicense=accept-securebackup-cookie;' \
	&& JAVA_HOME=$(ls -d /usr/local/jdk1.*) \
        && unzip -j -o /tmp/policy.zip -d $JAVA_HOME/jre/lib/security \
	&& rm /tmp/policy.zip

CMD /usr/local/netbeans/bin/netbeans
