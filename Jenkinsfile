pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building Python application...'
                bat 'python -m py_compile app.py'
            }
        }

        stage('Test/Validate') {
            steps {
                echo 'Validating application dependencies...'
                bat 'python -m pip install -r requirements.txt'
                bat 'python -m py_compile app.py'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                bat '"C:\\Users\\admin\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t sanskrit-multilingual-chatbot:latest .'
            }
        }

        stage('Result') {
            steps {
                echo 'Pipeline completed successfully!'
                echo 'Docker image created: sanskrit-multilingual-chatbot:latest'
            }
        }
    }
}
