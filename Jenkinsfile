pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                // Checkout from your Git repository
                git url: 'https://github.com/Ishrath625/CI-CD_Pipeline/', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                // Add your build commands here, e.g., sh 'mvn clean install'
            }
        }
    }

    post {
        always {
            script {
                // Capture the build logs
                def logContent = currentBuild.getLog(100) // Gets the last 100 lines of log

                // Send email with the build log
                mail to: 'your-email@example.com',
                     subject: "Build ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                     body: """\
                       Build Result: ${currentBuild.currentResult}
                       
                       Build Logs:
                       ${logContent}
                     """
            }
        }
    }
}
