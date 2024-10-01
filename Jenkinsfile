pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'python -m unittest discover'
            }
        }
        stage('Lint Code') {
            steps {
                sh 'flake8 .'
            }
        }
    }

    post {
        always {
            junit '**/test-reports/*.xml'
            cleanWs()
        }
    }
}
