pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            args '-v /var/jenkins_home:/var/jenkins_home'
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
