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
                bat 'php artisan build'  // Use 'bat' for Windows batch commands
            }
        }
    }
}


