pipeline {
    agent { docker 'hitalos/laravel' }
    stages {
        stage('Checkout from github') {
            steps {
                checkout scm
                sh 'composer install'
            }
        }
    }
    stages {
        stage('Checkout from github') {
            steps {
                sh 'docker run -p 8000:80 hitalos/laravel'
            }
        }
    }
}            
