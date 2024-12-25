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
                npm install
                ls -la
                test -f dpk.txt
                npm test
                '''
            
            }
        }
    }
}
