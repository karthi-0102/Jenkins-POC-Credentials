pipeline {
    agent any


    stages {
        stage('Checkout') {
            steps {
                // The checkout will now happen in a clean directory
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building..."'
            }
        }
    }
}
