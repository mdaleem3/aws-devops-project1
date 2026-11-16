pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/mdaleem3/aws-devops-project1'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t aleem-web:1.0 .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f aleem-web || exit 0'
                bat 'docker run -d --name aleem-web -p 8085:80 aleem-web:1.0'
            }
        }

        stage('Verify Application') {
            steps {
                bat 'curl.exe -I http://localhost:8085'
            }
        }
    }
}