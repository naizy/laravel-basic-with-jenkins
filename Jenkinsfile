node {
    stage('Configure') {
        env.PATH = "/usr/local/bin/:/usr/local/php5/bin:${env.PATH}"
    }

    stage('Checkout') {
        checkout scm
    }

    stage('Install Composer') {
        sh '''
            alias composer="php /usr/local/bin/composer.phar"
            composer install
        '''
    }
    
    stage ('Create env file'){
        sh '''
            cp .env.example .env
            php artisan key:generate
        '''
    }
}
