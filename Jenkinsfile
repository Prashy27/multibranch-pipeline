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
    }
}
