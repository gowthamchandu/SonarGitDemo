pipeline {
    agent any
    stages {
        stage('SonarQube Analysis') {
            steps {
                echo 'Preparing report...'
                withSonarQubeEnv('SonarScanner') {
                    sh "./script-file.sh"
                }
            }
        }
    }
}
