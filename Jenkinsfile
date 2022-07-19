node {
    stage('Checkout Code') {
        echo 'About to checkout ....'
        checkout scm
    }
    stage('Build Image') {
        def customImage = docker.build("prashantkumar14/python-flask-docker:${env.BUILD_ID}")
        docker.withRegistry( '', 'docker-hub-prashant' )
        {
            customImage.push(latest)
        }
    }
}