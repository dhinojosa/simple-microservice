node {
    git 'https://github.com/dhinojosa/simple-microservice.git'
    docker.build('simple-microservice')
    docker.withRegistry('https://219099013464.dkr.ecr.us-west-2.amazonaws.com', 'ecr:us-west-2:dhinojosa-aws') {
       docker.image('simple-microservice').push('latest')
    }
}
