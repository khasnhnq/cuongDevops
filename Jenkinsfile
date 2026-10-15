pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage completed'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESS'
        }
        failure {
            echo 'BUILD FAILED'
        }
    }
}
