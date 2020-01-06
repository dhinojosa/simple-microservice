pipeline {
	stages {
		agent('docker-agent') {
			stage('checkout') {
				scm checkout
			}
			stage('deploy') {
				docker.withRegistry('https://registry.example.com', credentials-id) {
					def image = docker.build("simple-microservice:${env.BUILD_ID}")
					image.push()
				}
			}
		}
	}
}
