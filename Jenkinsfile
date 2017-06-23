pipeline {
    agent any
    stages {
        stage('Checkout from github') {
            steps {
                checkout scm
            }
        }
        stage('Install composer packages') {
             steps {
                 sh '''
                    alias composer="php /usr/local/bin/composer.phar"
                    composer install
                '''
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
        
        stage ('Run Tests'){
             steps {
                echo 'Add tests here. if all good, continue to production, else exit and send error.'
             }
        }

        stage ('Move to production'){
             steps {
                sh '''
                    sudo cp -R ./ /Users/Naizy/Documents/links/
                    sudo chmod -R 777 /Users/Naizy/Documents/links/storage/ || true
                '''
             }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}  
