FROM jenkins/jenkins:latest

USER root
RUN apt-get update && \
    apt-get install -yq --no-install-recommends \
    curl \ 
    wget
# RUN curl -fsSL https://deb.nodesource.com/setup_12.x | bash - && \
RUN curl -fsSL https://deb.nodesource.com/setup_current.x | bash - && \
    apt-get install -y nodejs \
    build-essential && \
    node --version && \ 
    npm --version
RUN npm install -g newman
RUN mkdir /var/log/jenkins
RUN mkdir /var/cache/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins
RUN chown -R jenkins:jenkins /var/cache/jenkins
# RUN jenkins-plugin-cli --plugins oplugin-name
USER jenkins
ENV JAVA_OPTS="-Xmx8192m"