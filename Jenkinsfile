pipeline {
    agent {
        docker { image 'node:18-alpine' }
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('todo-app')
                }
            }
        }
        stage('Run Application') {
            steps {
                script {
                    docker.image('todo-app').run('-p 3000:3000')
                }
            }
        }
    }
}
