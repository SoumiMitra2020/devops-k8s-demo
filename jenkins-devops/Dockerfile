FROM jenkins/jenkins:lts

USER root

# Install basic tools
RUN apt-get update && apt-get install -y \
    curl \
    git \
    docker.io

# Install kubectl
RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl \
    && chmod +x kubectl \
    && mv kubectl /usr/local/bin/

# Install Helm
RUN curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

# Add Jenkins user to docker group
RUN usermod -aG docker jenkins

USER jenkins
