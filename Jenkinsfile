pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Build steps here
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Test steps here
                }
            }
        }
    }
    post {
        always {
            emailext(
                subject: 'Build ${BUILD_STATUS} - ${JOB_NAME}',
                body: '''
                    <html>
                        <body>
                            <h1>Build ${BUILD_STATUS}</h1>
                            <p>Build URL: <a href="${BUILD_URL}">${BUILD_URL}</a></p>
                            <p>Changes since last success:</p>
                            <ul>
                                ${CHANGES_SINCE_LAST_SUCCESS.collect { "<li>${it}</li>" }.join('\n')}
                            </ul>
                        </body>
                    </html>
                ''',
                recipientList: 'chaudhariganeshofficial@gmail.com',
                mimeType: 'html'
            )
        }
    }
}