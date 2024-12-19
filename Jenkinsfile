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
                    // Simulate generating the index.html file
                    echo 'Generating HTML report...'
                    writeFile file: 'index.html', text: '<html><body><h1>Sample Report</h1></body></html>'
                    // Replace this with your actual HTML report generation logic
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

            // Check if the report exists before sending the email
            script {
                def reportExists = fileExists 'index.html'
                if (reportExists) {
                    echo 'HTML report found. Sending email with attachment...'

                    // Send email with the generated HTML report attached
                    emailext(
                        subject: "Jenkins Pipeline Execution Complete - HTML Report",
                        body: "The Jenkins pipeline has finished executing. Please find the HTML report attached.",
                        to: 'ganeshchaudhari.dev@gmail.com',  // Use your provided email address here
                        attachmentsPattern: 'index.html'  // Attach the HTML report
                    )
                } else {
                    echo 'HTML report not found. Skipping email.'
                }
            }
        }
    }
}
