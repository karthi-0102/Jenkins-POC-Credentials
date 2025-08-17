pipeline {
    agent any
    stages {
        stage('Use Secret') {
            steps {
                // Use the ID you created, e.g., 'my-github-api-token'
                withCredentials([string(credentialsId: 'sample, variable: 'sample')]) {
                    
                    // The secret is now available in the SECRET_API_KEY environment variable
                    sh 'echo "Using the secret to perform an action..."'
                    sh "echo $sample"
                }
            }
        }
    }
}
