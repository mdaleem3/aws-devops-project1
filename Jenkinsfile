
pipeline {
    agent any

    stages {

        stage('Check Windows User') {
            steps {
                bat 'whoami'
            }
        }

        stage('Check Docker Path') {
            steps {
                bat 'where.exe docker'
            }
        }

        stage('Check Docker Version') {
            steps {
                bat '"C:\\Users\\Haseed\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" version'
            }
        }

        stage('Check Docker Engine') {
            steps {
                bat '"C:\\Users\\Haseed\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" -H npipe:////./pipe/dockerDesktopLinuxEngine ps'
            }
        }
    }
}
