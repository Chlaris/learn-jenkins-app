pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker-agent-pipeline {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                '''
            }
        }
    }
}