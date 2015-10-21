FROM 42nerds/base:trusty
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Add the oracle java repository and update apt cache
RUN add-apt-repository ppa:webupd8team/java -y && apt-get update -y

# Accept the license agreement
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections

# Install the installer
RUN apt-get install -y oracle-java8-installer

# Clean up
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Set $JAVA_HOME
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle