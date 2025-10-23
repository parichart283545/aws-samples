pipeline {
    agent {
        docker {
            image 'node:16-alpine' // Use a specific Node 16 Docker image
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/parichart283545/aws-samples.git' // Replace with your GitHub repository URL
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install --save' // Install dependencies, including saving to package.json
            }
        }
        stage('Run Unit Tests') {
            steps {
                sh 'npm test' // Execute your unit tests
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build' // Execute your build command (e.g., for creating production-ready assets)
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
