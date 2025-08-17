pipeline {
    // This tells Jenkins to run the stage inside a Docker container.
    // We use the official 'docker:latest' image which includes the Docker CLI.
    agent {
        docker { image 'docker:24.0' }
    }

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker --version'
                sh 'docker pull ubuntu:20.04'
                // Add your other docker commands here, like 'docker build', 'docker push', etc.
                echo 'Docker commands are running inside a temporary docker agent container!'
            }
        }
    }
}
