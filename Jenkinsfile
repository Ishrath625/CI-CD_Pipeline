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
                body: """
                    <p>Pipeline completed with status: ${currentBuild.currentResult}.</p>
                    <p>Please check the attached build log for details.</p>
                """,
                to: 'tkaushik130622@gmail.com',
                attachLog: true,  // This attaches the full build log
                mimeType: 'text/html'  // HTML formatting for the email body
            )
        }
    }
}
