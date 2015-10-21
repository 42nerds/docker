# This image is basically just ubuntu with sshd installed and configured
FROM 42nerds/ant:latest
MAINTAINER 42nerds - Inh. Julian Kaffke <info@42nerds.com>

# Installs i386 architecture as mentioned here: http://developer.android.com/sdk/installing/index.html?pkg=tools
RUN dpkg --add-architecture i386
RUN apt-get update -y
RUN apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1

# Clean up
RUN rm -rf /var/lib/apt/lists/*
RUN apt-get autoremove -y
RUN apt-get clean

# Define file and download
ENV ANDROID_FILE android-sdk_r24.4.1-linux.tgz
WORKDIR /opt
RUN wget -q http://dl.google.com/android/${ANDROID_FILE}
RUN tar xzf ${ANDROID_FILE}

# Clean update
RUN rm ${ANDROID_FILE} 

# Set env vars
ENV ANDROID_VERSIONS android-15,android-16,android-17,android-18,android-19,android-20,android-21 
ENV ANDROID_BUILD_TOOLS 21.1.0
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

# Update the sdk with specified versions and buildtools
RUN echo y | android update sdk --no-ui -a --filter tools,platform-tools,${ANDROID_VERSIONS},build-tools-${ANDROID_BUILD_TOOLS}
