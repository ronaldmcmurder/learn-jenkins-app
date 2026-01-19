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
                    npm config set registry https://registry.npmjs.org/
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}