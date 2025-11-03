pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Building branch: ${env.BRANCH_NAME}"
                checkout scm
            }
        }

        stage('Install & Test') {
            steps {
                sh 'node -v || true'
                sh 'npm --version || true'
                sh 'npm run test || true'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Simulating build for ${env.BRANCH_NAME}"'
                sleep 3
            }
        }
    }

    post {
        always {
            echo "✅ Build finished for ${env.BRANCH_NAME}"
        }
    }
}
