pipeline {
	agent any
		stages {
			stage('checkout') {
				scm checkout
			}
			stage('deploy') {
				def registryURL = '219099013464.dkr.ecr.us-west-2.amazonaws.com/docker-registry'
					docker.withRegistry('https://registry.example.com', credentials-id) {
					def image = docker.build("simple-microservice:${env.BUILD_ID}")
					image.push()
			}
			}
		}
}
