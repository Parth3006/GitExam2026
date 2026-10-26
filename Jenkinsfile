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
                bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" build -t ecommerce-app .'
                bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" run -d -p 8080:3000 --name my-ecommerce-container ecommerce-app'
            }
        }
    }
}
