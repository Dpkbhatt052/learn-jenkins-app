pipeline {
    agent any

    stages {
        stage('W/o Docker') {
            steps {
                sh '''
                   ls -la
                   touch dpk.txt
                   '''
            }
            
        }
        stage('Hello') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                node --version
                npm --version
                npm ci
                npm run build
                ls -la
                '''
            
            }
        }
    }
}
