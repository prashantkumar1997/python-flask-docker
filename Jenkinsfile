node {
    stage('Checkout Code') {
        echo 'About to checkout ....'
        checkout scm
    }
    stage('Build Image') {
        def customImage = docker.build("prashantkumar14/python-flask-docker")
        docker.withRegistry( '', 'docker-hub-prashant' )
        {
            customImage.push("${BRANCH_NAME}-${env.BUILD_ID}")
            customImage.push("latest")
        }
    }
}