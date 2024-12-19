pipeline {
    agent any
    stages {
        // ... your existing build and test stages ...

        stage('Send Email') {
            steps {
                
                mail body: '''
                    Hi Team,

                    Jenkins Build ${BUILD_NUMBER} has ${BUILD_STATUS}.

                    Check the console output at ${BUILD_URL} for more details.

                    Attached are the build reports.

                    Thanks,
                    Jenkins
                ''',
                subject: 'Jenkins Build ${BUILD_NUMBER} ${BUILD_STATUS}',
                to: 'chaudhariganeshofficial@gmail.com, ganeshchaudhari.dev@gmail.com'
            }
        }
    }
}