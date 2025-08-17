pipeline {
    // It's best practice to have no global agent
    agent none

    stages {
        stage('Pull Ubuntu Image') {
            // This tells Jenkins to run these steps inside a temporary container
            // The 'docker:latest' image contains the Docker CLI tools we need
            agent {
                docker { image 'docker:latest' }
            }
            steps {
                echo 'I am now running inside a Docker container agent!'
                
                // This command uses the Docker CLI available inside the agent
                sh 'docker pull ubuntu:24.04'
                
                echo 'Pull command finished. Now running other shell commands...'
                sh 'echo "Hello from the agent!"'
                sh 'ls -la'
            }
        }
    }
}
