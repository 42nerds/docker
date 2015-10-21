# This image is basically just ubuntu with sshd installed and configured
FROM 42nerds/jenkins-base:latest
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

#Install curl
RUN apt-get update && apt-get install -y curl

# Write the setup script to a file (piping directly to bash does NOT cause docker build to fail if curl isn't installed)
RUN curl -sL https://deb.nodesource.com/setup_0.12 > install_node.sh

# Run setup script
RUN bash install_node.sh

# And remove it 
RUN rm -f install_node.sh

#...and finally install nodejs
RUN apt-get install nodejs -y

CMD ["/usr/sbin/sshd", "-D"]