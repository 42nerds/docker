FROM 42nerds/android-sdk:latest
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

RUN curl -sL https://deb.nodesource.com/setup_0.12 > install_node.sh && \
    bash install_node.sh && \
    rm -f install_node.sh && \
    apt-get install -y nodejs openssh-server && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#Install cordova globally
RUN npm install -g cordova