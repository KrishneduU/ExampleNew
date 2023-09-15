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

      stage('Copy Folder to Tomcat Server') {
    steps {
        script {
            def tomcatServer = 'http://localhost:8082' // Replace with your Tomcat server's hostname or IP
            def tomcatUser = 'krish' // Replace with your Tomcat server's username
            def tomcatDestination = 'Tomcat 9.0\\webapps' // Replace with the destination path on the Tomcat server

            // Use the 'sh' step to execute the 'scp' command
            bat "scp -r ExJenkins ${tomcatUser}@${tomcatServer}:${tomcatDestination}"
        }
    }
}



        
    }
}


