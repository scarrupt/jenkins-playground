pipeline {
    agent {
        docker { image 'ubi9/openjdk-21:latest' }
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew clean build'
            }
        }
    }
}
