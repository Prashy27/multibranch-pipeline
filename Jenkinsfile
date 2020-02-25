pipeline {
    agent any
    environment {
        CI = 'true'
        HTTPS_PROXY = ''
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('docker-hello-world') {
            steps {
                sh 'sudo docker run hello-world'
            }
        }
        stage('docker-agent-test') {
            agent { docker { image 'maven:3-alpine' } }
            steps {
                sh 'echo docker agent test'
            }
        }
    }
}
