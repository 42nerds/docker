# This Dockerfile was inspired by https://github.com/evarga/docker-images
# This image is basically just ubuntu with sshd installed and configured
FROM 42nerds/java:7
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Install a basic SSH server
RUN apt-get update && apt-get install -y openssh-server

# Clean up
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Configure PAM 
RUN sed -i 's|session    required     pam_loginuid.so|session    optional     pam_loginuid.so|g' /etc/pam.d/sshd
RUN mkdir -p /var/run/sshd

# Add user jenkins to the image
RUN adduser --quiet jenkins

# Set password for the jenkins user (you may want to alter this).
RUN echo "jenkins:jenkins" | chpasswd

# Standard SSH port
EXPOSE 22


CMD ["/usr/sbin/sshd", "-D"]