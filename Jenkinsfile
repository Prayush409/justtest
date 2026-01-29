pipeline {
    agent any

    stages {
        stage('clone repo') {
            steps {
                echo 'Building..'
                 checkout scm
            }
        }
        stage('image build') {
            steps {
                echo 'Testing..'
                sh 'docker image build -t pythonimg:-1.1 .'
            }
        }
        stage('container build') {
            steps {
                echo 'Deploying....'
                 sh 'docker container run -d --name py_app -p 8080:5000 pythonimg:0.1'
            }
        }
    }
}

