pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Server Monitoring Dashboard'
                sh 'ls -l'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing required files'
                sh 'test -f index.html'
                sh 'test -f style.css'
                sh 'test -f script.js'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment simulated successfully'
                sh 'mkdir -p deployed'
                sh 'cp index.html style.css script.js deployed/'
                sh 'ls -l deployed'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful'
        }
        failure {
            echo 'Deployment failed'
        }
    }
}
