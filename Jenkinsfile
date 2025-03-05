pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                    args '--user=root'  // Allows full permissions inside the container
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
