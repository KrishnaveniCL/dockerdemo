node {
     //cleanup current user docker credentials
     sh 'rm  ~/.dockercfg || true'
     sh 'rm ~/.docker/config.json || true'
    
    stage('Clone repository') {
        git branch: "master", url: "https://github.com/ChetanKumar07/Sample-Docker-ECR.git"
    }
    stage('Build image') {
        sh "docker build -t 676488429201.dkr.ecr.us-east-2.amazonaws.com/ecr-docker:MyImage ."
    }
    stage('Push image') {
        docker.withRegistry('https://676488429201.dkr.ecr.us-east-2.amazonaws.com/ecr-docker', 'ecr:us-east-2:Aws-ecr') {
            sh "docker push 676488429201.dkr.ecr.us-east-2.amazonaws.com/ecr-docker:MyImage"
            //docker.image("MyImage").push()
        }
    }
}
