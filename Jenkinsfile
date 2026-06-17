pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Server Monitoring Dashboard'
                sh 'ls -l'
            }
        }

        stage('Test') {
            steps {
                echo 'Checking required files'
                sh 'test -f index.html'
                sh 'test -f style.css'
                sh 'test -f script.js'
            }
        }

        stage('Deploy to Nginx') {
            steps {
                echo 'Deploying dashboard to Nginx'
                sh '''
                rm -rf /var/www/html/*
                cp index.html style.css script.js /var/www/html/
                ls -l /var/www/html/
                '''
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
