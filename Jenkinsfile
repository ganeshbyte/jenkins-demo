=pipeline {
    agent any
    stages {
        // ... your existing build and test stages ...

        stage('Send Email') {
            steps {
                script {
                    // Use 'findFiles' to get the list of report files
                    def reportFiles = findFiles(glob: '*.html').collect { it.path }
                    env.REPORT_FILES = reportFiles.join(",")
                }
                emailext body: '''
                    Hi Team,

                    Jenkins Build ${BUILD_NUMBER} has ${BUILD_STATUS}.

                    Check the console output at ${BUILD_URL} for more details.

                    Attached are the build reports.

                    Thanks,
                    Jenkins
                ''',
                subject: "Jenkins Build ${BUILD_NUMBER} ${BUILD_STATUS}",
                to: 'chaudhariganeshofficial@gmail.com, ganeshchaudhari.dev@gmail.com',
                attachmentsPattern: '${REPORT_FILES}'
            }
        }
    }
}
