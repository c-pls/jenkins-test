pipeline {
    environment{
        registry = "core-harbor.local/test"
        registryCredential = "harbor_creds"
        dockerImage = ''
    }
    agent {
        dockerfile true
    }
    stages {
        stage('Build') {
            steps {
                script {
                    dockerImage = docker.build('your-image-name:latest', '-f Dockerfile .')
                }
            }
        }
    }
}
