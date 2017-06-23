node {

    stage('Configure system') {
        env.PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
    }
    stage('Checkout from github') {
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
    
    stage ('Move to production'){
        sh '''
            cp -R ./ /Users/Naizy/Documents/links/
            chmod -R 777 /Users/Naizy/Documents/links/storage/ || true
        '''
    }
}
