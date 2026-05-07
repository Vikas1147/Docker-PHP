pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t php-docker-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop php-container || exit 0'
                bat 'docker rm php-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 9090:80 --name php-container php-docker-app'
            }
        }
    }
}