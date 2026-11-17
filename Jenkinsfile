stage('Docker Verification') {
    steps {
        bat '''
            echo Checking Docker location
            where.exe docker

            echo Checking Docker version
            docker --version

            echo Checking Docker daemon
            docker info
        '''
    }
}
