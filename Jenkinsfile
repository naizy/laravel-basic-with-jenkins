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
}
