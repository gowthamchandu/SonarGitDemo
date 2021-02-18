pipeline {
    agent any
    stages {
        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'SonarScanner'
            }
            steps {
                echo 'Preparing report...'
                withSonarQubeEnv('SonarServer') {
                    sh "mvn sonar:sonar"
                }
            }
        }
	stage('Quality Gate') {
	    steps {
		timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
                }
	    }
	
	}
	stage('Deployment') {
            steps {
		echo 'Deployment stage....'
  	    }
	}
    }
}
