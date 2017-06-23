pipeline {
    agent { docker 'hitalos/laravel' }
    stages {
        stage('Checkout from github') {
            steps {
                checkout scm
                sh 'composer install'
            }
        }
        stage('Deploy') {
            steps {
                sh '/usr/bin/docker run -p 8000:80 hitalos/laravel'
            }
        }
    }
}            
