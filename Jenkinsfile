pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ShaheenaShahbas476/jenkins.git'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh """
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install pytest
                    pytest -q
                """
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
                sh 'echo Deployment Successful!'
            }
        }
    }
}
