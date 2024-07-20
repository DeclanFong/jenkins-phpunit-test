pipeline {
    agent {
        docker {
            image 'composer:latest'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                // Check out the Git repository
                git url: 'https://github.com/DeclanFong/jenkins-phpunit-test.git'
            }
        }
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
