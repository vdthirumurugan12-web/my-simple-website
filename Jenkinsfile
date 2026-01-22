pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This step pulls your code from your repository (GitHub/GitLab)
                checkout scm
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Checking file integrity...'
                // Basic check to ensure the main file exists
                sh 'test -f index.html'
                echo 'HTML file found!'
            }
        }

        stage('Deploy Prep') {
            steps {
                echo 'Archiving files for deployment...'
                // This saves your files as an "Artifact" in Jenkins
                archiveArtifacts artifacts: 'index.html, style.css, script.js', fingerprinted: true
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully! Your website is ready.'
        }
        failure {
            echo 'Something went wrong with the pipeline.'
        }
    }
}
