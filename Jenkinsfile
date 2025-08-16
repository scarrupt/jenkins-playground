pipeline {
    agent {
        docker {
            image 'registry.access.redhat.com/ubi9/openjdk-21'
            args '-e DOCKER_HOST=$DOCKER_HOST -e DOCKER_TLS_VERIFY=$DOCKER_TLS_VERIFY -e DOCKER_CERT_PATH=$DOCKER_CERT_PATH -v /certs/client:/certs/client'
        }
    }
    stages {
        stage('Build') {
            steps {
                writeFile file: '.testcontainers.properties', text: 'docker.client.strategy=org.testcontainers.dockerclient.EnvironmentAndSystemPropertyClientProviderStrategy'
                sh './gradlew clean build'
            }
        }
    }
}
