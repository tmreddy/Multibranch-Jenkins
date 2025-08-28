pipeline {
    agent any

    environment {
        APP_NAME = "Python-Jenkins-App"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out develop branch"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Installing dependencies for develop branch..."
                sh 'pip install -r requirements.txt'
                echo "Develop-specific build steps placeholder"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests for develop branch..."
                sh 'pytest -v'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying develop branch to staging environment..."
                sh 'echo "Staging deploy placeholder"'
            }
        }
    }

    post {
        always {
            echo "Pipeline finished for develop branch"
        }
        success {
            echo "Pipeline succeeded!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}

