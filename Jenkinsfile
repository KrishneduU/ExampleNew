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
                echo 'composer install'
            }
        }
        stage('Build and Deploy') {
            steps {
                echo 'php artisan config:cache'
                echo 'php artisan route:cache'
                echo 'php artisan migrate --force'
                // Add any other necessary Laravel commands here
            }
        }
         stage('Run') {
            steps {
                echo 'php artisan serve'
                
            }
        }
        stage('Package as WAR') {
            steps {
                // Create a WAR file from your Laravel project
                echo 'php artisan package:war'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                ech"Deploy the WAR file to Tomcat (using the Deploy to Container Plugin)"
                //deploy adapters: [tomcat(credentialsId: 'your-tomcat-credentials', url: 'http://tomcat-server:8080/manager/text', path: '/your-app', war: '**/your-app.war')], contextPath: '', failOnError: true
            }
        }
        
    }
}


