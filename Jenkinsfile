node {

    stage('Checkout from github') {
        checkout scm
    }

    stage('Install composer packages') {
        sh '''
            alias composer="/usr/local/php5/bin/php /usr/local/bin/composer.phar"
            composer install
        '''
    }
    
    stage ('Create laravel env'){
        sh '''
            cp .env.example .env
            php artisan key:generate
            chmod -R 777 storage/ || true
        '''
    }
}
