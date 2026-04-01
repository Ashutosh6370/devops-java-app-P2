pipeline {
    agent any

    environment {
        IMAGE_NAME = "ashutosh6370/devops-java-app-P2"
        IMAGE_TAG = "v1"
        CONTAINER_NAME = "devops-java-app-P2"
    }

    tools {
        maven 'Maven3.8.7'
        jdk 'JDK17'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Ashutosh6370/devops-java-app-P2.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                }
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push $IMAGE_NAME:$IMAGE_TAG'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop $CONTAINER_NAME || true
                docker rm $CONTAINER_NAME || true
                docker run -d --name $CONTAINER_NAME $IMAGE_NAME:$IMAGE_TAG
                '''
            }
        }
    }
}
