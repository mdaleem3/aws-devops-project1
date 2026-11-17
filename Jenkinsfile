
pipeline {
    agent any

    stages {

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
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t aleem-cicd:v1 .'
            }
        }

        stage('Verify Docker Image') {
            steps {
                bat 'docker images aleem-cicd'
            }
        }

stage('Run Docker Container') {
    steps {
        bat '''
            docker rm -f aleem-container 2>NUL
            docker run -d --name aleem-container -p 8085:80 aleem-cicd:v1
            docker ps
        '''
    }
}

    }
}
