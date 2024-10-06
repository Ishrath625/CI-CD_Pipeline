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
                // Get the last 100 lines of the build log
                def buildLog = currentBuild.rawBuild.getLog(100).join('\n')
                emailext (
                    subject: "${currentBuild.fullDisplayName} - Build #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                    body: """\
                        Build log:
                        ${buildLog}
                        
                        Job: ${env.JOB_NAME}
                        Build Number: ${env.BUILD_NUMBER}
                        Status: ${currentBuild.currentResult}
                    """,
                    to: 'tkaushik130622@gmail.com'  // Replace with your recipient email
                )
            }
        }
    }
}
