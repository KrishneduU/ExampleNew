pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                sh 'php artisan build'
            }
               
        }

        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'php artisan test'
            }
        }

        stage('Build and Deploy') {
            steps {
                sh 'php artisan optimize'
                sh 'npm install'
                sh 'npm run production'
                // Add deployment steps here
            }
        }
    }
}

