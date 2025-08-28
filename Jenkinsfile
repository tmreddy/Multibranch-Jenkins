pipeline {
    agent any

    environment {
        APP_NAME = "Python-Jenkins-App"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out feature branch"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Installing dependencies for feature branch..."
                sh 'pip install -r requirements.txt'
                echo "Feature-specific build steps placeholder"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests for feature branch..."
                sh 'pytest -v'
            }
        }

        stage('Deploy') {
            steps {
                echo "Feature branch: no deploy"
            }
        }
    }

    post {
        always {
            echo "Pipeline finished for feature branch"
        }
        success {
            echo "Pipeline succeeded!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}

