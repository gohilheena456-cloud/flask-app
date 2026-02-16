pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git 'https://github.com/gohilheena456-cloud/flask-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Restart Application') {
            steps {
                sh 'pm2 restart flask-app || pm2 start app.py --name flask-app --interpreter python3'
            }
        }
    }
}

