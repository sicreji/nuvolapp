pipeline {
    agent {
        docker {
            image 'node:14.16-alpine'
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
