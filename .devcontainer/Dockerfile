FROM ubuntu:22.04
 
# Update and install packages
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && \
    apt-get dist-upgrade -y && \
    apt-get autoremove --purge -y && \
    apt-get install -y \
    build-essential \
    chrpath \
    cpio \
    curl \
    debianutils \
    diffstat \
    file \
    gawk \
    gcc \
    git \
    iputils-ping \
    libegl1-mesa \
    libsdl1.2-dev \
    liblz4-tool \
    locales \
    mesa-common-dev \
    python3 \
    python3-pip \
    python3-pexpect \
    python3-git \
    python3-jinja2 \
    python3-subunit \
    socat \
    texinfo \
    tree \
    unzip \
    wget \
    xz-utils \
    zstd && \
    rm -rf /var/lib/apt/lists/*
 
# Change locale
RUN dpkg-reconfigure locales \
 && locale-gen en_US.UTF-8 \
 && update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
 
ENV LC_ALL   en_US.UTF-8
ENV LANG     en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
 
# Create the user
ARG USERNAME=dev
ARG USER_UID=1001
ARG USER_GID=$USER_UID
 
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m -s /bin/bash $USERNAME
 
# Switch user
USER dev
 
# User settings
WORKDIR /home/dev
RUN bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)" \
    && sed -i -e "s/\"font\"/\"nwinkler\"/" .bashrc
