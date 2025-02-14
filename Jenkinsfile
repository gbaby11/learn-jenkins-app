pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker{
                    image 'node:18-alphine'
                    reuseNode true
                }
            }
            steps{
                sh '''
                    ls -la
                    npm --version
                    node --version
                    npm -c
                    npm run build
                    ls -la
                '''
            }
            
        }
        stage('Test'){
            steps{
                sh "test -d build"
            }
        }
    }
}