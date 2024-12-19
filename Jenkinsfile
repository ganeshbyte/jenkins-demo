pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code (not needed in this case)'
            }
        }

        stage('Build') {
            steps {
                echo 'Running build steps (or any other steps you need)'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution complete.'

            // Send an email notification
            emailext(
                subject: "Jenkins Pipeline Execution Complete",
                body: "The Jenkins pipeline has finished executing successfully.",
                to: 'chaudhariganeshofficial@gmail.com'  // Replace with your email address
            )
        }
    }
}
