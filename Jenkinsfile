pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code (not needed in this case)'
            }
        }

        stage('Generate HTML Report') {
            steps {
                script {
                    // Let's make sure index.html is being created
                    echo 'Generating HTML report...'
                    // Simulating HTML report generation (if not using an actual process)
                    writeFile file: 'index.html', text: '<html><body><h1>Sample Report</h1></body></html>'
                    
                    // Alternatively, ensure that your actual HTML report generation command is in place here
                }
            }
        }

        stage('Publish HTML Report') {
            steps {
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

            // Ensure the file exists before attempting to send the email
            script {
                // Check if the report exists in the workspace
                def reportExists = fileExists 'index.html'
                if (reportExists) {
                    echo 'HTML report found. Sending email with attachment...'

                    // Send email with the HTML report attached
                    emailext(
                        subject: "Jenkins Pipeline Execution Complete - HTML Report",
                        body: "The Jenkins pipeline has finished executing. Please find the HTML report attached.",
                        to: 'chaudhariganeshofficial@gmail.com',  // Replace with your Gmail address
                        attachmentsPattern: 'index.html'  // Attach the HTML report
                    )
                } else {
                    echo 'HTML report not found. Skipping email.'
                }
            }
        }
    }
}
