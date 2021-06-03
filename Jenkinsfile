pipeline {
	agent any

	tools {
		maven 'maven3'
	}

	stages {
		stage('Maven Build') {
			steps {
				sh "mvn clean package"
			}
		}

		stage('Docker Build Image') {
			steps {
				sh 'echo "Hello Jenkins"'
			}
		}
	}
}