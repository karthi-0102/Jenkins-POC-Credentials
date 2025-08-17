pipeline {
    // It's best practice to have no global agent
   agent {
    docker { image "docker:20.10.24-dind" }
}


    stages {
        stage('Pull Ubuntu Image') {
            // This tells Jenkins to run these steps inside a temporary container
            // The 'docker:latest' image contains the Docker CLI tools we need
            steps {
                echo 'I am now running inside a Docker container agent!'
                
                // This command uses the Docker CLI available insid
                sh 'echo "Hello from the agent!"'
                sh 'ls -la'
            }
        }
    }
}
