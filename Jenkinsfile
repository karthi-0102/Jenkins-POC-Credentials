pipeline {
    agent any

    // Add this options block to automatically clean the workspace
    options {
        cleanWs()
    }

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
