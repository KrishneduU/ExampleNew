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
        // Deploy the WAR file to Tomcat using the credentials you created
        deploy adapters: [tomcat(credentialsId: 'krish/******', url: 'http://tomcat-server:8082/manager/text', path: 'ExJenkins')], contextPath: 'my-app'
    }
}


        
    }
}


