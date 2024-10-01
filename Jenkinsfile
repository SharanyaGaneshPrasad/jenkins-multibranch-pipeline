pipeline {
    agent any

    stages {
        stage('Checkout Feature branch') {
            steps {
                checkout scm
            }
        }
        stage('Install dependencies of feature') {
            steps {
                echo 'Install dependencies from requirements.txt inside feature'
            }
        }
        stage('Run Tests') {
            steps {
              echo 'Run tests inside feature'
            }
        }
        stage('Deploy  Code') {
            steps {
                echo 'deploy to ECR from feature'
            }
        }
    }
}
