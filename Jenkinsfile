pipeline {
	agent any
	stages {
		stage('checkout') {
			steps {
				scm 'https://github.com/dhinojosa/simple-microservice.git'
			}
		}
		stage('deploy') {
			steps {
				docker.withRegistry('219099013464.dkr.ecr.us-west-2.amazonaws.com/docker-registry','dhinojosa') {
					def image = docker.build("simple-microservice:${env.BUILD_ID}")
					image.push()
				}
			}
		}
	}
}
