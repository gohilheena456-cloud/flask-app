pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/gohilheena456-cloud/flask-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Start/Restart App') {
            steps {
                sh '''
                pm2 restart flask-app || pm2 start app.py --name flask-app --interpreter python3
                '''
            }
        }
    }
}
