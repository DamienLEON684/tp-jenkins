pipeline {
    agent any 
    stages {
        stage('Clean Workspace') {
            steps {
                echo '--- Cleaning the workspace ---'
                cleanWs()
            }
        }
        stage('Build') {
            steps {
                echo '--- Simulating a build by creating a fake artifact ---'
                bat 'mkdir build\\libs'
                bat 'echo "This is a fake jar file" > build\\libs\\my-app-1.0.jar'
            }
        }
        stage('Test') {
            steps {
                echo '--- Simulating tests by creating a fake JUnit report ---'
                bat 'mkdir build\\reports'
                writeFile file: 'build/reports/TEST-report.xml', text: '''
<testsuite tests="1" failures="0" errors="0">
    <testcase classname="my.test" name="myTest"/>
</testsuite>
'''
            }
        }
    }
    post {
        always {
            echo '--- Archiving artifacts and recording test results ---'
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/reports/**/*.xml'
        }
    }
}
