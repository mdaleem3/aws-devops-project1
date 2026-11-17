
pipeline {
    agent any

    stages {

        // Stage 1
        stage('Docker Verification') {
            steps {
                bat '''
                    echo Checking Docker location
                    where.exe docker

                    echo Checking Docker version
                    docker --version

                    echo Checking Docker Engine
                    docker info
                '''
            }
        }

        // Stage 2
        stage('Build Docker Image') {
            steps {
                bat '''
                    docker build -t aleem-cicd:v1 .
                '''
            }
        }

        // Stage 3
        stage('Verify Docker Image') {
            steps {
                bat '''
                    docker images
                '''
            }
        }

    }
}
