pipeline {
    agent any

    environment {
        APP_NAME = "Python-Jenkins-App"
        VENV_DIR = "venv"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out feature branch"
                checkout scm
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo "Setting up Python virtual environment..."
                sh """
                    # Create virtual environment if it doesn't exist
                    python3 -m venv ${VENV_DIR}
                    # Upgrade pip inside the venv
                    ${VENV_DIR}/bin/pip install --upgrade pip
                """
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing dependencies for feature branch..."
                sh """
                    # Install dependencies from requirements.txt
                    ${VENV_DIR}/bin/pip install -r requirements.txt
                """
            }
        }
        
        stage('Build') {
            steps {
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

