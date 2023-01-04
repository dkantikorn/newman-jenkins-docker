# jenkins standalone with doxker 

## Docker build
```bash
    $ docker build -t jenkins-stanalone -f stanalone/Dockerfile .
```
## Docker run
```bash
    $ docker run -p 50000:50000 -p 8080:8080 --name=jenkins-stanalone jenkins-stanalone
```

## Run with docker compose
```bash
    $ docker compose up [-d]
    $ docker compose stop
    $ docker compose start
```

## Jenkins Pipeline
```groovy
pipeline {
    agent any
    
    stages {
            
        stage('Cloning Git') {
        steps {
            git branch: 'main',url: 'https://github.com/dkantikorn/newman-jenkins-docker.git'
        }
        }
        
        stage('Install dependencies') {
        steps {
            sh 'npm install'
        }
        }
        
        stage('Automate test') {
        steps {
            sh 'npm run api-tests-production'
        }
        }      
    }
    }
```