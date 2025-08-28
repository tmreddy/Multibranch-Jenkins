pipeline {
    agent any

    environment {
        APP_NAME = "Python-Jenkins-App"
        VENV_DIR = "venv"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out develop branch"
                checkout scm
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo "Setting up Python virtual environment..."
                sh """
                    # Create virtual environment if it doesn't exist
                    python3 -m venv ${VENV_DIR}
                    # Activate venv
                    . venv/bin/activate
                    # Upgrade pip inside the venv
                    pip install --upgrade pip
                    # Install dependencies into venv
                    pip install -r requirements.txt
                """
            }
        }

        // stage('Install Dependencies') {
        //     steps {
        //         echo "Installing dependencies for develop branch..."
        //         sh """
        //             # Install dependencies from requirements.txt
        //             ${VENV_DIR}/bin/pip install -r requirements.txt
        //         """
        //     }
        // }
        
        stage('Build') {
            steps {
                echo "Develop-specific build steps placeholder"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests for develop branch..."
                sh 'venv/bin/pytest -v'
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

