pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Repository cloned'
            }
        }

        stage('Create venv and Install') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                python -m pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                . venv/bin/activate
                PYTHONPATH=. python -m pytest
                '''
            }
        }

        stage('Run App') {
            steps {
                sh '''
                . venv/bin/activate
                python app.py
                '''
            }
        }
    }
}