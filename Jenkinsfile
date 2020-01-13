node {
	stages {
		stage('Checkout') {
			steps {
				git 'https://github.com/dhinojosa/simple-microservice.git'
			}
		}
		stage('Build Container') {
			steps {
				docker.build('simple-microservice')
			}
		}
		stage('Push to ECR') {
			steps {
				docker.withRegistry('https://219099013464.dkr.ecr.us-west-2.amazonaws.com', 'ecr:us-west-2:dhinojosa-aws') {
					docker.image('simple-microservice').push('latest')
				}
			}
		}
	}
}
