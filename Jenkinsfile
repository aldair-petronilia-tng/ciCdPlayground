pipeline {
    agent any
    
    tools {
        nodejs 'yarn'
    }

    stages {
        stage('install') {
            steps {
                sh 'yarn'
            }
        }
        stage('build') {
            steps {
                sh 'yarn build'
            }
        }
        stage('test') {
            steps {
                sh 'yarn test'
            }
        }
        stage('E2E tests') {
            steps {
                sh 'yarn test:e2e'
            }
        }
    }

    post {
        success {
            currentBuild.description = "Build Successful - Version 1.0.0"
        }
        failure {
            currentBuild.description = "Build Failed - Check logs for details"
        }
        always {
            junit '**/reports/**/*.xml'
        }
    }
}
