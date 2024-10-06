pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
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
                body: """Pipeline completed with status: ${currentBuild.currentResult}.
                         Please check the attached build log for details.""",
                to: 'tkaushik130622@gmail.com',
                attachLog: true,  // This attaches the full build log
                mimeType: 'text/plain'  // Plain text for simplicity
            )
        }
    }
}
