pipeline{
    agent any

    environment {
        registry = "127266170878.dkr.ecr.ap-south-1.amazonaws.com/ecr"    
    }

    stages {
        stage ('Checkout'){
            steps{
               checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/charankmar6/ecr.git']]])
            }
        }
        stage('Docker Build'){
            steps {
                   script {
                        dockerImage = docker.build registry
                    }


            }
       }
    }    
}
