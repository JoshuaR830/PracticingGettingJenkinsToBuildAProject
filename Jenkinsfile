pipeline {
    agent {
        docker {
            image 'node:12'
            args '-p 2345:80'
        }
    }
    stages {
        stage('Initialize'){
            steps {
                def dockerHome = tool 'myDocker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"
            }
        }
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