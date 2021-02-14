pipeline {
    agent any
    stages {
        stage('SonarQube Analysis') {
            steps {
                echo 'Preparing report...'
                withSonarQubeEnv('Sonar2Server') {
                    sh "./script-file.sh"
                }
            }
        }
    }
}
