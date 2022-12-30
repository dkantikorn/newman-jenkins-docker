pipeline {
    agent any
    stages {
            
        // stage('Cloning Git') {
        //     steps {
        //         echo 'Clone source code from git repository.'
        //         git 'https://github.com/dkantikorn/newman-jenkins-docker.git'
        //     }
        // }
        
        stage('Install dependencies') {
            steps {
                echo 'Install for node dependencies.'
                sh 'npm install'
            }
        }
        
        stage('Automate test') {
            steps {
                echo 'Run automation test with newman '
                sh 'cd /var/jenkins_home/newman-jenkins-docker && npm run api-tests-production'
            }
        }      
    }
}