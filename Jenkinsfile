@Library('shared-library') _

pipeline {
    agent any
    stages {
        stage('echo env info') {
            steps {
                script {
                    printEnvInfo()
                }
            }
        }
    }
}