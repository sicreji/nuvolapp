pipeline {
    agent {
        node {
            label 'docker-agent-nodejs'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/sicreji/nuvolapp.git'
                sh '''
                npm install
                npm run build
                '''
            }
        }
       
    }
}
