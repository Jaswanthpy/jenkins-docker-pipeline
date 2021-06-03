pipeline {
	agent any

	tools {
		maven 'maven3'
	}

	stages {
		stage('Hello') {
			steps {
				sh 'echo "Hello jenkins test!"'
			}
		}

		stage('Maven Build') {
			steps {
				sh 'mvn clean package'
			}
		}
	}
}