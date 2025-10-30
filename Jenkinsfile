@Library('shared-library') _

pipeline {
    agent any
    stages {
        stage('echo env info') {
            steps {
                script {
                    sendNotification(
                        color: 'good',
                        message: "Build #${env.BUILD_NUMBER} of job ${env.JOB_NAME} is running."
                    )
                    printEnvInfo()
                }
            }
        }
    }
}