pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo 'Cloning Done'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-web apache-web/'
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
