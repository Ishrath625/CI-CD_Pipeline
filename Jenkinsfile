pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example for Java: sh 'mvn clean install'
                echo 'Build completed.'
            }
        }
    }

    post {
        always {
            echo 'Sending email notification with build log...'
            
            // Using emailext to send an email with build log attached
            emailext (
                subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                body: """
                    <p>Pipeline completed with status: ${currentBuild.currentResult}</p>
                    <p>Check the attached build log for details.</p>
                """,
                to: 'tkaushik130622@gmail.com',
                attachLog: true, // This attaches the entire build log
                mimeType: 'text/html' // For rendering HTML email body
            )
        }
    }
}
