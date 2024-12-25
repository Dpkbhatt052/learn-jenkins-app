pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Dpkbhatt052/learn-jenkins-app.git'
            }
        }
        
        stage('W/o Docker') {
            steps {
                sh '''
                   ls -la
                   touch dpk.txt
                   touch d.txt
                   touch ram.txt
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
                ls -la
                test -f dpk.txt
                '''
            
            }
        }
    }
}
