pipeline {
	agent any
		stages {
			stage('checkout') {
				steps {
					scm checkout
				}
			}
			stage('deploy') {
				steps {
						docker.withRegistry('219099013464.dkr.ecr.us-west-2.amazonaws.com/docker-registry', credentials-id) {
						def image = docker.build("simple-microservice:${env.BUILD_ID}")
						image.push()
				}
			}
			}
		}
}
