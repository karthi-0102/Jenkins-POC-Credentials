pipeline {
    agent {
        docker { image 'ubuntu:20.04' }
    }

    environment {
        // Define a credential parameter.
        // The 'credentials()' helper will fetch the credential from Jenkins' credential store.
        // 'github-credentials' is the ID of the credential you need to set up in Jenkins.
        // This should be a "Secret Text" or "Username and Password" type credential.
      //  GIT_CREDENTIALS = credentials('github-credentials')
      CRED  = credentials('cred')
    }

    stages {
        stage('Checkout Source Code') {
            steps {
                // This step checks out the source code from the SCM configured in the Jenkins job.
                // It will use the configured SCM (e.g., Git) and the credentials if the repository is private.
                echo 'Checking out source code...'
                checkout scm
                echo 'Checkout complete.'
            }
        }

        stage('Use Credentials') {
            steps {
                // Example of how to use the credential.
                // In a real pipeline, you would use this for things like logging into a private registry,
                // deploying to a server, or authenticating with a service.
                
                // IMPORTANT: Avoid echoing secrets directly to the console in a production environment.
                // This is for demonstration purposes only.
                sh 'echo "Using the credential to perform some action..."'
                sh 'echo $CRED'

                // For a "Secret Text" credential, you can use it as an environment variable.
                // For "Username and Password", you can access them via `${GIT_CREDENTIALS_USR}` and `${GIT_CREDENTIALS_PSW}`.
                // This example assumes a "Secret Text" credential.
                sh 'echo "The secret credential is: $CRED"'

                echo "Credential usage example complete."
            }
        }
        
        stage('List files') {
            steps {
                echo "Listing files in the workspace:"
                sh 'ls -la'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
