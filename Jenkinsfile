pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/muniprakash04/frontend.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r build/* /var/www/html/
                sudo systemctl restart nginx
                '''
            }
        }

    }
}
