pipeline {
    agent any
    stages {
        stage('Send Email') {
            steps {
              
                mail body: '''
                        Hi Team,

                        Jenkins Build ${BUILD_NUMBER} has ${BUILD_STATUS}.

                        Check the console output at ${BUILD_URL} for more details.

                        Thanks,
                        Jenkins
                    ''',
                    to: 'chaudhariganeshofficial@gmail.com, ganeshchaudhari.dev@gmail.com',
                    attachmentsPattern: 'index.html'
                
            }
        }
    }
}
