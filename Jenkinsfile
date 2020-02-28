pipeline {
    agent any
    stages {
        stage('Build') { 
            {
                
            steps {
                docker {
                    image 'node:latest' 
                    args '-p 3000:3000' 
                }
            }
                sh 'npm install' 
            }
        }
    }
}

