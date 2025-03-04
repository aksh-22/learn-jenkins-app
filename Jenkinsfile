pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                script {
                    sh '''
                        which docker
                        docker --version
                        ls -la
                        node -v
                        npm -v
                        npm ci
                        npm run build
                    '''
                }
            }
        }
    }
}
