pipeline {
    agent any
    triggers{
        pollSCM('H/5 * * * *')
    }
    stages {
        stage('Build') {
            steps {
                echo "Connection successful"
            }
        }
        stage('Deploy with Docker') {
            steps {
                bat '"C:\\Users\\USER\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t ecommerce-app .'
                bat '"C:\\Users\\USER\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" rm -f my-ecommerce-container || exit /b 0'
                bat '"C:\\Users\\USER\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" run -d -p 9090:3000 --name my-ecommerce-container ecommerce-app'
            }
        }
    }
}
