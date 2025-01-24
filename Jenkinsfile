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
}
