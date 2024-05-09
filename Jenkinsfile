pipeline {
    environment{
        registry = "core-harbor.local/test"
        registryCredential = "harbor_creds"
        dockerImage = ''
    }
    agent any
    stages {
        stage('Build image') {
            steps {
                script {
                    dockerImage = docker.build registry + ":$BUILD_NUMBER"
                    }
            }
        }
    }
}
