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
