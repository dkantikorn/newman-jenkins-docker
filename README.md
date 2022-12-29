# jenkins2-with-docker
Learning :: How to install/config the Continuous Integration Server with Jenkins on Docker 

* Jenkins master 
* Jenkins data to keep all configuration such as plugins and jobs of Jenkins

## Doker image
$ docker pull jenkins/jenkins:latest
$ docker pull --platform linux/x86_64 debian:jessie (for Apple silicon M1)

## Jenkins master
$ docker build -t jenkins-master -f master/Dockerfile .

## Jenkins data
$ docker build -t jenkins-data -f data/Dockerfile .

## Run Jenkins data first
$ docker run --name=jenkins-data jenkins-data

## Run Jenkins master
$ docker run -p 8080:8080 -p 50000:50000 --name=jenkins-master --volumes-from=jenkins-data -d jenkins-master

## Open Browser http://localhost:8080
$ docker exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword