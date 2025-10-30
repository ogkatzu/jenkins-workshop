@Library('shared-library') _

pipeline {
    agent {
        label 'maven'
    }
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
        stage('build with recovery') {
            steps {
                container('maven') {
                    script {
                        buildWithRecovery(environment: 'prod')
                    }
                }
            }
        }
        stage('build with health check') {
            steps {
                container('maven') {
                    script {
                        withHealthCheck(url: 'https://www.google.com') {
                            sh "mvn --version"
                        }
                    }
                }
            }
        }
    }
}