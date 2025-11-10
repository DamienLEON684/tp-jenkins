pipeline {
    agent any 
    stages {
        stage('Build and Test') { 
            steps {
                echo '--- Checking Docker Version ---'
                bat 'docker run --rm node:24.11.0-alpine3.22 node --version'
                echo '--- Listing Environment Variables ---'
                bat 'set' 
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful (Pipeline OK!)'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}
