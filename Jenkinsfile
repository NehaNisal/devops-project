pipeline {
    agent { label 'worker' }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/NehaNisal/devops-project.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                sudo apt update
                sudo apt install apache2 -y
                sudo systemctl start apache2
                sudo cp -r apache-web/* /var/www/html/
                '''
            }
        }
    }
}
