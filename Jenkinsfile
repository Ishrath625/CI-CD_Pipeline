pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }
    }

    post {
        always {
            echo 'Sending fallback email notification...'
            
            mail to: 'tkaushik130622@gmail.com',
                 subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Pipeline completed with status: ${currentBuild.currentResult}"
        }
    }
}
