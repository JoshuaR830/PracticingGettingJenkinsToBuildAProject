pipeline {
    agent {
        docker {
            image 'node:12'
            args '-p 2345:80'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                npm install
            }
        }
        stage ('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}