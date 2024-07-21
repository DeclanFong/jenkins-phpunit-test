pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/DeclanFong/jenkins-phpunit-test.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    docker.image('composer:latest').inside {
                        sh 'composer install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('php:latest').inside {
                        sh 'phpunit'
                    }
                }
            }
        }
    }
}
