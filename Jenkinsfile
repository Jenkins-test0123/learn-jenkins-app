pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                cleanWS()
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
        stage('test') {
            steps{
                sh '''
                echo 'Test stage'
                cat index.html
                npm test
                '''
            }
        }
    }
}
