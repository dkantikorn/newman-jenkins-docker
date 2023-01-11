pipeline {
    agent any
    stages {
            
        stage('Install node dependencies') {
            steps {
                echo 'Install for node dependencies.'
                sh 'npm install'
            }
        }
        
        stage('Automate test simple') {
            steps {
                echo 'Run Newman automation test simple'
                sh 'npm run api-tests-production'
            }
        }  

        stage('Automate test with env') {
            steps {
                echo 'Run newman automation test with environment'
                sh 'npm run api-tests-production-env'
            }
        }     


         stage('Automate test with env and data') {
            steps {
                echo 'Run newman automation test with environmen and data'
                sh 'npm run api-tests-production-env-data'
            }
        }     
    }
}
