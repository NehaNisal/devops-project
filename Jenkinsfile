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
                dir('apache-web') {
                    sh 'docker build -t devops-web .'
                }
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop web || true'
                sh 'docker rm web || true'
                sh 'docker run -d -p 8081:80 --name web devops-web'
            }
        }

        stage('Verify') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
}
