# This image is basically just ubuntu with sshd installed and configured
FROM 42nerds/android-sdk:latest
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Install Node.js
# Write the setup script to a file (piping directly to bash does NOT cause docker build to fail if curl isn't installed)
RUN curl -sL https://deb.nodesource.com/setup_0.12 > install_node.sh

# Run setup script
RUN bash install_node.sh

# And remove it 
RUN rm -f install_node.sh

#...and finally install nodejs and openssh
RUN apt-get install -y nodejs openssh-server

# Clean up
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#Install cordova globally
RUN npm install -g cordova

# Configure PAM 
RUN sed -i 's|session    required     pam_loginuid.so|session    optional     pam_loginuid.so|g' /etc/pam.d/sshd
RUN mkdir -p /var/run/sshd

# Add user jenkins to the image
RUN adduser --quiet jenkins

# Set password for the jenkins user (you may want to alter this).
RUN echo "jenkins:jenkins" | chpasswd

# Set ENV vars again after adding jenkins user
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

# Standard SSH port
EXPOSE 22


CMD ["/usr/sbin/sshd", "-D"]