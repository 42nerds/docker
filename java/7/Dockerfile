FROM 42nerds/base:trusty
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

RUN add-apt-repository ppa:webupd8team/java -y && \
    apt-get update -y && \ 
    echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get install -y oracle-java7-installer && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV JAVA_HOME /usr/lib/jvm/java-7-oracle