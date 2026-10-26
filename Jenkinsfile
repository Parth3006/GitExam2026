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
                sh 'docker build -t ecommerce-app .'
                sh 'docker run -d -p 8080:3000 --name my-ecommerce-container ecommerce-app'
            }
        }
    }
}
