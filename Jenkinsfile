pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            args '--user=root'  // Allows full permissions inside the container
            reuseNode true
        }
    }
    
    stages {
        stage('Build') {
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
