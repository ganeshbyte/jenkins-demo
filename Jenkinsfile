pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Build your project here
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Test your project here
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Deploy your project here
                }
            }
        }
        stage('Send Email') {
            steps {
                mail body: '''
                    Hi Team,

                    Jenkins Build ${BUILD_NUMBER} has ${BUILD_STATUS}.

                    Check the console output at ${BUILD_URL} for more details.

                    Thanks,
                    Jenkins
                ''',
                subject: 'Jenkins Build ${BUILD_NUMBER} ${BUILD_STATUS}',
                to: 'recipient1@example.com, recipient2@example.com'
            }
        }
    }
}