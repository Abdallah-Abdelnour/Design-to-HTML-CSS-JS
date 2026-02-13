pipeline {
    agent any

    environment {
        IMAGE_NAME = "abdelnour46/landing-page"
    }
  
    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Abdallah-Abdelnour/Design-to-HTML-CSS-JS.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                    sh 'docker push $IMAGE_NAME'
                }
            }
        }
    }
}
