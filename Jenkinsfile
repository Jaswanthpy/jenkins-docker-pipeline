pipeline {
	agent any

	tools {
		maven 'maven3'
	}

	stages {
		stage('Maven Build') {
			steps {
				sh "echo ${getLatestCommitId()}"
				sh "mvn clean package"
			}
		}

		stage('Docker Build Image') {
			steps {
				sh "docker build . -t rjaswanth09/2021myapp:${getLatestCommitId()}"
			}
		}

		stage('Push to docker hub') {
			steps{
				withCredentials([usernameColonPassword(credentialsId: 'docker-hub', variable: 'dockerPWD')]) {
					sh "docker login -u rjaswanth09 -p ${dockerPWD}"
					sh "docker push rjaswanth09/2021myapp:${getLatestCommitId()}"
				}
			}
		}
	}
}


def getLatestCommitId() {
	def commitId = sh returnStdout: true, script: 'git rev-parse --short HEAD'
	return commitId
}