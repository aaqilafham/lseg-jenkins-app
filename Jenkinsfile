pipeline {
    agent any
    stages {
      stage('DockerAgent') {
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
                npm ci
                npm run build
                ls -la
                '''
            }
        }
    }
}
