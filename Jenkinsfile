pipeline {
    agent any 
    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }

    stages {
        stage('Test Environment Variables') {
            steps {
                echo "Database engine is ${DB_ENGINE}"
                echo "DISABLE_AUTH is ${DISABLE_AUTH}"
                echo "--- Affichage de toutes les variables ---"
                bat "set"
            }
        }
    }
}
