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
                sh 'docker image build -t pythonimg:0.1 .'
            }
        }
        stage('container build') {
            steps {
                echo 'Deploying....'
                 sh 'docker container run -d --name py_app -p 8080:6060 pythonimg:0.1'
            }
        }
    }
}

