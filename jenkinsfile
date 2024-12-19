pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // If you are working with a Git repository, this step checks out the code
                // For now, since you have the file locally, you can skip this or add your own SCM configuration.
                echo 'Checking out code (not needed in this case)'
            }
        }

        stage('Publish HTML Report') {
            steps {
                // Publish the index.html as a report
                echo 'Publishing HTML report...'
                publishHTML(target: [
                    reportName: 'Sample HTML Report',   // Name of the report displayed in Jenkins
                    reportDir: '.',                     // Directory containing the HTML file (current directory here)
                    reportFiles: 'index.html'          // Name of the HTML file to publish
                ])
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution complete.'
        }
    }
}
