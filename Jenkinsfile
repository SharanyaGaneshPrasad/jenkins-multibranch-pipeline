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
                echo 'Install dependencies from requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'python3 -m unittest discover'
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
