pipeline {
   agent any 
    stages {
      stage('GetSCM') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/ChetanKumar07/Docker-ECR.git'
         }
         }
         stage('Image Build'){
             sh "docker build --build-arg APP_NAME=receipts -t 531359658382.dkr.ecr.ap-south-1.amazonaws.com/node_app:MyImage"
         }
         stage('Push Image'){
         docker.withRegistry('https://531359658382.dkr.ecr.ap-south-1.amazonaws.com/node_app', 'ecr:ap-south-1:AWS_ECR') {
            sh "docker push 531359658382.dkr.ecr.ap-south-1.amazonaws.com/node_app:MyImage"
            }
         }
    }
    
}
