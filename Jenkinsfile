pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            args '--entrypoint=""'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install' // Use bat instead of sh for Windows
            }
        }
        stage('Run Tests') {
            steps {
                bat 'npm test' // Add if you have tests
            }
        }
        stage('Build Application') {
            steps {
                bat 'npm run build' // Replace with your build command if applicable
            }
        }
    }
}
