
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Docker Check') {
            steps {
                bat 'docker version'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t aleem-web:%BUILD_NUMBER% .'
            }
        }

        stage('Stop Old Container') {
            steps {
                script {
                    bat(
                        returnStatus: true,
                        script: 'docker rm -f aleem-web'
                    )
                }
            }
        }

        stage('Deploy Container') {
            steps {
                bat 'docker run -d --name aleem-web -p 8085:80 aleem-web:%BUILD_NUMBER%'
            }
        }

        stage('Verify Application') {
            steps {
                bat 'curl.exe -f http://localhost:8085'
            }
        }
    }
}
