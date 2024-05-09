pipeline {
    environment{
        registry = "core-harbor.local"
        registryCredential = "harbor-credentials"
        dockerImage = ''
        repo = "test"
        imageTag = "latest"
    }
    agent any
    stages {
        stage('Build image') {
            steps {
                script {
                    dockerImage = docker.build registry + "/$repo"+ ":$imageTag"
                    }
            }
        }

        stage('Deploy image') {
            steps {
                script {
                    docker.withRegistry(registry, registryCredential){
                        dockerImage.push()
                    }
                }
            }
        }
    }
}
