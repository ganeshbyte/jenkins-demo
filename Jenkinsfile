pipeline {
    agent any
    stages {
        // ... your existing build and test stages ...

        stage('Send Email') {
            steps {
                emailext (
                    attachLog: true,
                    attachmentsPattern: 'index.html',  // Ensure 'index.html' exists as an artifact
                    body: 'Bhai Ho Jao Please',
                    subject: 'Bhai Ho Jao Please',
                    to: 'chaudhariganeshofficial@gmail.com'
                )
            }
        }
    }
}
