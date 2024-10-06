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
            echo 'Sending fallback email notification...'
            
            mail to: 'tkaushik130622@gmail.com',
                 ssubject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                 body: """Pipeline completed with status: ${currentBuild.currentResult}.
                         Please check the attached build log for details.""",
                attachLog: true,  // This attaches the full build log
                mimeType: 'text/plain'  // Plain text for simplicity

        }
    }
}
