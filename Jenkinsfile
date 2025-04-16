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
                ls -la
                npm --version
                npm ci
                npm run build
                ls -la
                echo 'Hello World'
            }
        }
    }
}
