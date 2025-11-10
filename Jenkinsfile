pipeline {
    agent any
    stages {
        stage('Test inside Container') {
            steps {
                echo '--- Running node command inside a Linux container (from our Windows agent) ---'
                bat 'docker run --rm node:24.11.0-alpine3.22 node --eval "console.log(process.arch, process.platform)"'
            }
        }
    }
    post {
        success {
            echo 'Pipeline successful'
        }
    }
}
