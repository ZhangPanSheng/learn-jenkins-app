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
                    
                    npm ci
                    npm run build
                    ls -la
                   '''
            }
        }
        stage('Test'){
            steps{
                sh 'test -f build/index.html'
            }
        }
    }
}
