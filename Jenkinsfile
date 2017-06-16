pipeline {
    
    agent any
    
    environment { 
        composer="php /usr/local/bin/composer.phar"
        PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
    }
    
    stages {
        stage('Checkout from github') {
            steps {
                echo env.PATH
                checkout scm
            }
        }
        stage('Install composer packages') {
            steps {
                sh 'composer install'
            }
        }
        stage ('Create laravel env'){
            steps {
                sh '''
                    cp .env.example .env
                    php artisan key:generate
                    chmod -R 777 storage/ || true
                '''
            }
        }
    }    
}
