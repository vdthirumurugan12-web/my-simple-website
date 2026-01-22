pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/my-website.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp index.html style.css script.js /var/www/html/
                '''
            }
        }

        stage('Verify') {
            steps {
                sh 'ls /var/www/html/'
            }
        }
    }
}
