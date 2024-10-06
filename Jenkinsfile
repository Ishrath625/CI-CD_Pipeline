pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Simulating some log output
                echo 'Running build process...'
                echo 'Build completed successfully.'
            }
        }
    }

    post {
        always {
            echo 'Sending email notification with build log attached...'
            
            emailext (
                subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                body: """<html>
                            <body>
                                <h2>Pipeline Notification</h2>
                                <p>Pipeline completed with status: <strong>${currentBuild.currentResult}</strong>.</p>
                                <p>Please check the attached build log for details.</p>
                            </body>
                          </html>""",
                to: 'tkaushik130622@gmail.com',
                attachLog: true,  // Attach the full build log
                mimeType: 'text/html'  // HTML formatting for the email body
            )
        }
    }
}
