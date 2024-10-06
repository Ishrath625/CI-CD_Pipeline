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
            echo 'Sending email notification...'
            mail to: 'tkaushik130622@gmail.com',
                 subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Pipeline completed with status: ${currentBuild.currentResult}"
        }
    }
}
