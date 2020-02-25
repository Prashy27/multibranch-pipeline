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
        stage('docker-test') {
            steps {
                sh 'docker run hello-world'
            }
        }
    }
}
