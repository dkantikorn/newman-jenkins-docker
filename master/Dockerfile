## Jenkins Master
FROM jenkins/jenkins:latest

USER root
# RUN apt-get update && apt-get install -y ruby make more-thing-here
RUN mkdir /var/log/jenkins
RUN mkdir /var/cache/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins
RUN chown -R jenkins:jenkins /var/cache/jenkins
USER jenkins
ENV JAVA_OPTS="-Xmx8192m"
# ENV JENKINS_OPTS --httpPort=-1 --httpsPort=7000
# ENV JENKINS_SLAVE_AGENT_PORT 50001
# EXPOSE 7000