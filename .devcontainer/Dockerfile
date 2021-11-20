# for format details, see https://docs.docker.com/engine/reference/builder/

# select image
# see here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.195.0/containers/cpp/.devcontainer/base.Dockerfile
ARG VARIANT="debian-11"
FROM mcr.microsoft.com/vscode/devcontainers/cpp:${VARIANT}
LABEL author="dariocurr@gmail.com" maintainer="dariocurr@gmail.com" version="0.0.1"

# update apt
RUN apt update \
	&& apt upgrade -y \
	&& export DEBIAN_FRONTEND=noninteractive

# add zsh configuration and replace oh-my-zsh with antigen
USER vscode
WORKDIR /home/vscode/
RUN rm -r .oh-my-zsh \
	&& git clone https://github.com/zsh-users/antigen.git .antigen
COPY .devcontainer/.zshrc .