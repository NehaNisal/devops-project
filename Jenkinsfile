pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/NehaNisal/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-web apache-web/'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker stop web || true'
                sh 'docker rm web || true'
                sh 'docker run -d -p 8081:80 --name web devops-web'
            }
        }

        stage('Done') {
            steps {
                echo 'Auto Deploy Successful'
            }
        }
    }
}
    
