pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/melaxa12311/devops-platform'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t melaxa75722/devops-platform .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop devops-app || true'
                sh 'docker rm devops-app || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name devops-app melaxa75722/devops-platform'
            }
        }
    }
}

