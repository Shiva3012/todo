pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            args '--entrypoint=""'
        }
    }
    environment {
        // Convert the Jenkins working directory path for Docker compatibility
        WORKDIR = "${pwd()}".replaceAll('\\\\', '/').replaceAll('C:', '/c')
    }
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    sh "docker run -v ${WORKDIR}:${WORKDIR} -w ${WORKDIR} node:18-alpine npm install"
                }
            }
        }
    }
}
