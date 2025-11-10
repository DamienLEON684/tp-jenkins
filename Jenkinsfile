/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'docker run --rm node:24.11.0-alpine3.22 node --version'
            }
        }
    }
}
