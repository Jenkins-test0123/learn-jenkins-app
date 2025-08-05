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
                sh '''
                    echo "📁 Listing current directory:"
                    ls -la

                    echo "📦 Node & NPM versions:"
                    node --version
                    npm --version

                    echo "📦 Running npm ci..."
                    npm ci --loglevel=verbose

                    echo "⚙️ Running build..."
                    npm run build --loglevel=verbose

                    echo "📁 Final directory state:"
                    ls -la
                '''
            }
        }
    }
}
