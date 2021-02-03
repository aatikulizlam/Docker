FROM php:8-cli

# Configure apt
ENV DEBIAN_FRONTEND=noninteractive
ENV ACCEPT_EULA=Y
RUN apt update && apt -y install --no-install-recommends apt-utils apt-transport-https debconf-utils gcc build-essential 2>&1

# Install git, process tools
RUN apt update && apt-get -y install git procps

# Zip for composer
RUN set -eux; apt-get update; apt-get install -y libzip-dev zlib1g-dev; docker-php-ext-install zip

# APT Upgrade
RUN apt update && apt -y upgrade 

# Set the default shell to bash instead of sh
ENV SHELL /bin/bash