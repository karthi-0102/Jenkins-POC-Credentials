pipeline {
    agent any
    stages {
        stage('Use Secret') {
            steps {
                // Correct syntax: credentialsId and variable are separate arguments
                withCredentials([string(credentialsId: 'sample', variable: 'sample')]) {
                    
                    // The secret is now available in the 'sample' environment variable
                    sh 'echo "Using the secret to perform an action..."'

                    // IMPORTANT: Never print secrets in a real pipeline.
                    // This is just for demonstration. Jenkins will mask it.
                    sh 'echo "The secret value is ${sample}"'
                }
            }
        }
    }
}
