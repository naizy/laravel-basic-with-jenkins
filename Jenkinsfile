pipeline {
    
    agent any
    
    stages {
        stage('Checkout from github') {
            steps {
                checkout scm
            }
        }
        stage('Install composer packages') {
            environment {
                env.PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
                PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
            }
            steps {
                echo "${PATH}"
                echo "${env.PATH}"
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
