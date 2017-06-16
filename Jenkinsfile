node {
    stage('Configure') {
        echo env.PATH
        env.PATH = "/usr/local/bin/:${env.PATH}"
        echo env.PATH
    }

    stage('Checkout') {
        checkout scm
    }

    stage('Install Composer') {
        sh '''
            alias composer="php /usr/local/bin/composer.phar"'
            composer install
        '''
    }
}
