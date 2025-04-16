pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
               sh '''
                ls -la
                npm --version
                npm ci
                npm run build
                ls -la
                echo 'Hello World'
                '''
            }
        }
        stage('Test'){
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
            sh '''
            echo 'Test Stage'
            test -f build/index.html
            npm test
            '''
            }
        }
    }
}
