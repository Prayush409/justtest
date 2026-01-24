pipeline {
    agent any

    environment {
        IMAGE_NAME = "prayushmaharjan/pythonapp"
    }

    stages {

        stage('Clone Repo') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f python-app || true
                docker run -d --name python-app -p 6060:5000 $IMAGE_NAME:latest
                '''
            }
        }
    }
}

