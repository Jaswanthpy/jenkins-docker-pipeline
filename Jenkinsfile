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
				sh 'sudo docker build . -t rjaswanth09/2021myapp'
				sh 'echo "hello docker"'
			}
		}
	}
}