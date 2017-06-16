node {
    
    agent any
    
    environment { 
        PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
    }
    
    stage('Checkout from github') {
        echo env.PATH
        checkout scm
    }

    stage('Install composer packages') {
        sh '''
            alias composer="php /usr/local/bin/composer.phar"
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
