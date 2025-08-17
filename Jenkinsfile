pipeline {
    agent {
        docker {
            image 'registry.access.redhat.com/ubi9/openjdk-21'
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
