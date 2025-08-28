pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'python3 setup.py install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pytest'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to production...'
                // Add deployment steps here
            }
        }
    }
}

