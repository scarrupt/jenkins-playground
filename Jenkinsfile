pipeline {
    environment {
        TESTCONTAINERS_HOST_OVERRIDE = 'localhost'
    }

    agent {
        docker {
            image 'registry.access.redhat.com/ubi9/openjdk-21'
            args '--env DOCKER_HOST=tcp://docker:2376 --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=0 --network=host -v /certs/client:/certs/client:ro'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew clean build'
            }
        }
    }
}
