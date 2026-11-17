
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
                stage('Check Workspace Files') {
    steps {
        bat '''
            echo Checking workspace files
            dir

            echo Checking Dockerfile
            if exist Dockerfile (
                echo Dockerfile found successfully
            ) else (
                echo Dockerfile NOT found
                exit /b 1
            )
        '''
        
stage('Build Docker Image') {
    steps {
        bat 'docker build -t aleem-cicd:v1 .'
    }
}

    }
}
            }
        }

    }
}
