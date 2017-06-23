pipeline {
    agent { docker 'hitalos/laravel' }
    stages {
        stage('Checkout from github') {
            steps {
                checkout scm
                sh 'composer install'                
                sh 'cd /usr/bin/'                
                sh 'ls'
            }
        }
        stage('Deploy') {
             steps {
                 sh 'sudo docker run -p 8000:80 hitalos/laravel'
             }
         }
    }
}            
