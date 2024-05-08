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
                npm --version
                npm test
                npm --version
                ls -la
                '''
            }
        }
      stage ('FilesPath') {
        agent {
                docker {
                  image 'node:18-alpine'
                  reuseNode true
                }
            }
        steps {
            sh '''
             test -f build/index.
             npm test
            '''
        }
      }   
    }
}