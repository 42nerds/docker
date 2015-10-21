# This Dockerfile was inspired by https://github.com/evarga/docker-images
# This image is basically just ubuntu with sshd installed and configured
FROM 42nerds/base:latest
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Make sure the package repository is up to date.
RUN apt-get update
RUN apt-get -y upgrade

# Install git
RUN apt-get install -y git

# Install a basic SSH server
RUN apt-get install -y openssh-server

# Configure PAM 
RUN sed -i 's|session    required     pam_loginuid.so|session    optional     pam_loginuid.so|g' /etc/pam.d/sshd
RUN mkdir -p /var/run/sshd

# Install JDK 7 (latest edition)
RUN apt-get install -y openjdk-7-jdk

# Add user jenkins to the image
RUN adduser --quiet jenkins

# Set password for the jenkins user (you may want to alter this).
RUN echo "jenkins:jenkins" | chpasswd

# Standard SSH port
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]