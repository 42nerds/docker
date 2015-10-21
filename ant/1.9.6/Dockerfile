FROM 42nerds/java:7
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Set Ant version
ENV ANT_VERSION 1.9.6

# Download binaries
RUN cd &&  wget -q http://mirror.serversupportforum.de/apache//ant/binaries/apache-ant-${ANT_VERSION}-bin.tar.gz

# Untar
RUN tar xzf apache-ant-${ANT_VERSION}-bin.tar.gz

# Move to /opt/
RUN mv apache-ant-${ANT_VERSION} /opt/ant

# Clean up
RUN rm -f apache-ant-${ANT_VERSION}-bin.tar.gz

# Set env vars
ENV ANT_HOME /opt/ant
ENV PATH ${PATH}:/opt/ant/bin

