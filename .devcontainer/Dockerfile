FROM ubuntu:20.04

# This Dockerfile adds a non-root user with sudo access.
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Set the default user
USER $USERNAME

# ENV TZ=Europe/Paris
# RUN sudo ln -snf /usr/share/zoneinfo/$TZ /etc/localtime 
# RUN sudo touch /etc/timezone
# RUN sudo echo $TZ > /etc/timezone
# RUN DEBIAN_FRONTEND=noninteractive TZ=Europe/Paris sudo apt-get -y install tzdata

RUN sudo apt-get clean
RUN sudo apt-get update --fix-missing
RUN sudo apt-get install gnupg -y \
    && sudo apt-get install git -y \
    && sudo apt-get install python3-pip -y \
    && sudo apt-get install apt-transport-https -y \
    && sudo apt-get install vim -y \
    && sudo apt-get install curl -y \
    && sudo apt-get install unzip -y \
    && sudo apt-get install nano -y \
    && sudo apt-get install psmisc -y \
    && sudo apt-get install debconf-utils -y \
    && sudo apt-get install gnupg2 -y
RUN sudo apt-get update --fix-missing
RUN export EDITOR="/usr/bin/nano"

# install nodejs 18.x and stuff
RUN sudo curl -sL https://deb.nodesource.com/setup_18.x | sudo bash -
RUN sudo apt-get install -y nodejs
RUN sudo npm i -g gitmoji-cli@7.0.1

WORKDIR /app_testmoji