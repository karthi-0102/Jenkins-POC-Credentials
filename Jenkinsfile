pipeline {
    agent any
    stages {
        stage('Advanced Unmasking for Debugging') {
            steps {
                withCredentials([string(credentialsId: 'sample', variable: 'MY_SECRET')]) {
                    script {
                        // Step 1: Base64 encode the secret in Groovy.
                        // The Jenkins log filter will not recognize this encoded string as a secret.
                        def encodedSecret = MY_SECRET.bytes.encodeBase64().toString()

                        // Step 2: Pass the ENCODED secret to the shell and decode it there.
                        // ☢️ WARNING: EXTREME SECURITY RISK.
                        sh """
                            #!/bin/bash
                            echo "This is the encoded secret Jenkins sees (safe to print): ${encodedSecret}"
                            
                            # Use the 'base64' command to decode the string back to its original form.
                            DECODED_SECRET=\$(echo "${encodedSecret}" | base64 --decode)
                            
                            echo "Unmasked secret (for debugging only): \${DECODED_SECRET}"
                        """
                    }
                }
            }
        }
    }
}
