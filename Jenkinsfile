pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building DevOps project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t devops-web:latest .'
            }
        }

        stage('Docker Deploy') {
            steps {
                sh 'docker stop devops-webs-container || true'
                sh 'docker rm devops-webs-container || true'
                sh 'docker run -d --name devops-webs-container -p 8081:80 devops-web:latest'
            }
        }
    }
}
