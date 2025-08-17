pipeline {
    agent any
    stages {
        stage('Reveal Secret for Debugging') {
            steps {
                withCredentials([string(credentialsId: 'sample', variable: 'MY_SECRET')]) {
                    
                    // This is the standard, secure way. Jenkins will mask it.
                    sh 'echo "Attempting to print directly (will be masked): ${MY_SECRET}"'
                    
                    // ⚠️ DANGEROUS: This bypasses the masking for debugging.
                    sh '''
                        #!/bin/bash
                        # By assigning the secret to a new shell variable, we can bypass the log mask.
                        UNMASKED_SECRET="${MY_SECRET}"
                        echo "Unmasked secret (for debugging only): ${UNMASKED_SECRET}"
                    '''
                }
            }
        }
    }
}
