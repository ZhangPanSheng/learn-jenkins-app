pipeline {
    agent any

    stages {
        stage('Bilud') {
            agent {
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -l
                    npm --version
                    node --version
                    ls -la
                    npm ci
                    npm run build
                   '''
            }
        }
    }
}
