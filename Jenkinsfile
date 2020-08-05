node {
     //cleanup current user docker credentials
     sh 'rm  ~/.dockercfg || true'
     sh 'rm ~/.docker/config.json || true'
    
    stage('Clone repository') {
        git branch: "master", url: "https://github.com/ChetanKumar07/Sample-Docker-ECR.git"
    }
    stage('Build image') {
        sh "docker build -t 531359658382.dkr.ecr.ap-south-1.amazonaws.com/node_app:MyImage ."
    }
    stage('Push image') {
        docker.withRegistry('531359658382.dkr.ecr.ap-south-1.amazonaws.com/node_app', 'ecr:ap-south-1:AWS_ECR') {
            sh "docker push 531359658382.dkr.ecr.ap-south-1.amazonaws.com/node_app:MyImage"
            //docker.image("MyImage").push()
        }
    }
}
