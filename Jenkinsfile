pipeline {
    
    agent any
    
    stages {
        stage('Checkout from github') {
            steps {
                env.PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
                checkout scm
            }
        }
        stage('Install composer packages') {
            steps {
                alias composer="php /usr/local/bin/composer.phar"
                sh "composer install"
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
