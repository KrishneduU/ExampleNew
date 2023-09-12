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
                bat 'composer install' // Use 'bat' for Windows batch commands
            }
        }
        
        stage('Build') {
            steps {
               
                bat 'php artisan key:generate'
                bat 'php artisan migrate'
            }
        }
        stage('Test') {
            steps {
               bat 'php artisan test'
                // bat './vendor/bin/phpunit'
            }
        }
    }
}


