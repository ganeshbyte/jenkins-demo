pipeline {
    agent any
    stages {
        stage('Send Email') {
            steps {
                emailext (
                    // attachLog: true,
                    attachmentsPattern: 'index.html',
                    body: 'Bhai Ho Jao Please',
                    subject: 'Bhai Ho Jao Please',
                    to: 'chaudhariganeshofficial@gmail.com'
                )
            }
        }
    }
}
