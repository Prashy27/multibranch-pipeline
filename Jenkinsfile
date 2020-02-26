pipeline {
    agent any
    environment {
        registry = "prashaanth27/hello-world"
        registryCredential = ‘dockerhub’
        CI = 'true'
    }
    stages {
        stage('Build') {
            agent { docker { image 'maven:3-alpine' } }
            steps {
                sh 'mvn clean package'
            }
        }
        stage('upload docker image to dockerhub') {
            steps {
                withDockerRegistry([ credentialsId: "dockerhub", url: "https://index.docker.io/v1/" ]) {
                    sh 'docker push prashaanth27/hello-world:0.1'
                }
            }
        }
//        stage('docker-hello-world') {
//            steps {
//                sh 'sudo docker run hello-world'
//            }
//        }
//        stage('docker-agent-test') {
//            agent { docker { image 'maven:3-alpine' } }
//            steps {
//                sh 'echo docker agent test'
//            }
//        }
    }
}
