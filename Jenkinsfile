pipeline {
    agent any
    stages {
        // ... your existing build and test stages ...

        stage('Send Email') {
            steps {
                 emailext attachLog: true, attachmentsPattern: 'text', body: 'Bhai Ho Jao Please', subject: 'Bhai Ho Jao Please', to: 'chaudhariganeshofficial@gmail.com',attachmentsPattern:'index.html'
                    
            }
        }
    }
}