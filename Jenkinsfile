pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version 
                    npm ci || cat /home/node/.npm/_logs/*-debug-*.log
                    npm run build
                '''
            }
        }
    }
}