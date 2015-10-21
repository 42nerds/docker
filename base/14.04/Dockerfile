FROM ubuntu:trusty
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Update apt cache and upgrade
RUN apt-get update && apt-get upgrade -y

# Install common libraries
RUN apt-get install -y curl wget git vim software-properties-common

# Clean up
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*