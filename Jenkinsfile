pipeline {

    agent any

    triggers {
        pollSCM('* * * * *')   // Poll every minute for changes (auto-trigger)
    }

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
                pip install pytest
                pytest -q
                """
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                sh 'echo "Deployment Successful!"'
            }
        }
    }
}
