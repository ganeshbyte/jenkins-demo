pipeline {
    agent any
    stages {
        // ... your existing build and test stages ...

        stage('Send Email') {
            steps {
                 mail body: 'Test Message',
                    subject: 'Test Subject',
                    to: 'ganeshchaudhari.dev@gmail.com'
            }
        }
    }
}