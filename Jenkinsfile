pipeline {
    agent { docker { image 'maven:3-alpine' } }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('upload docker image to dockerhub') {
            steps {
                sh 'docker push prashaanth27/hello-world:0.1'
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
