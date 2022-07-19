node {
    stage('Checkout Code') {
        echo 'Checkout Code'
        checkout scm
    }
    stage('Build Image') {
        echo 'Build and Push Image'
        docker.withRegistry( 'docker.io/prashantkumar14/', 'docker-hub-prashant' )
        {
            def customImage = docker.build("python-flask-docker")
            customImage.push("${BRANCH_NAME}-${env.BUILD_ID}")
            customImage.push("latest")
        }
    }
}