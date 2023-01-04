pipeline {
    agent any
    stages {
            
        stage('Install node dependencies') {
            steps {
                echo 'Install for node dependencies.'
                sh 'npm install'
            }
        }
        
        stage('Automate test') {
            steps {
                echo 'Run automation test with newman '
                sh 'npm run api-tests-production'
            }
        }      
    }
}
