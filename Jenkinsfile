pipeline {
    agent {
        docker {
            image 'composer:latest'
        }
    }
    stages {
        stage('Build') {
            steps {
                // Install PHP dependencies using Composer
                sh 'composer install'
            }
        }
        stage('Test') {
            steps {
                // Run PHPUnit tests
                sh './vendor/bin/phpunit tests'
            }
        }
    }
}
