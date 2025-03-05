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
                        echo "Building application..."
                        ls -la
                        node -v
                        npm -v
                        npm ci
                        npm run build
                    '''
                }
            }
        }

        stage('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                script {
                    sh '''
                        echo "Running tests..."
                        node -v
                        npm -v
                        npm test
                    '''
                }
            }
        }
    }
}
