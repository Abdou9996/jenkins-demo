pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Repository cloned'
            }
        }

        stage('Install') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }

        stage('Run App') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}