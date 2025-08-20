pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Cut Masked Secret') {
            steps {
                withCredentials([string(credentialsId: 'sample', variable: 'MY_SECRET')]) {
                    sh 'echo "Piping the secret directly to cut..."'
                    
                    // The 'cut' command will receive '****' as input
                    sh 'echo "${MY_SECRET}" | cut -c 1-5'
                    sh 'echo "The user who triggered this build is: $github_user"'
                }
            }
        }
    }
}
