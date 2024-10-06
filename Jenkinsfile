pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Your build steps go here
                echo 'Building...'
            }
        }
    }

    post {
        always {
            script {
                def buildLog = currentBuild.getLog(100).join('\n')
                emailext (
                    subject: "${currentBuild.fullDisplayName} - Build #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                    body: """\
                        Build log:
                        ${buildLog}
                        
                        Job: ${env.JOB_NAME}
                        Build Number: ${env.BUILD_NUMBER}
                        Status: ${currentBuild.currentResult}
                    """,
                    to: 'tkaushik130622@gmail.com'
                )
            }
        }
    }
}
