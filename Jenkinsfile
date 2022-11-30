pipeline {
    
    agent any
    
    environment {     
        DOCKERHUB_CREDENTIALS= credentials('sicreji')     
    } 
    
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
       
        stage('Login to Docker Hub') {      	
            steps{                       	
	            sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                		
	            echo 'Login Completed'      
            }           
        }
        
        stage('Push Image to Docker Hub') {         
            steps{                            
                sh 'sudo docker push <dockerhubusername>/<dockerhubreponame>:$BUILD_NUMBER'           
                echo 'Push Image Completed'       
            }            
        }
    } // stages
    
    post{
        always {  
	    sh 'docker logout'     
    }      
}
} // pipeline
