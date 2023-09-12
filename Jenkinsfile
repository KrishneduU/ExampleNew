pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'composer install --no-interaction --prefer-dist'
            }
        }
        
        stage('Build') {
            steps {
                sh 'php artisan build'  // Replace with your Laravel build command
            }
        }
    }
}


