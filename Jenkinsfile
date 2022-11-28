pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t nuvolapp:latest .
                '''
            }
        }
        
        stage('Test') {
            steps {
                sh '''
                echo "Tests happen here"
                '''
            }
        
        }
       
        stage('Publish'){
            steps {
                // figuring out how to publish to dockerhub
                
            }
        
        }
    }
}
