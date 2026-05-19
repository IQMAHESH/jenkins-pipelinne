pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/IQMAHESH/jenkins-pipelinne.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop myapp-container || true'
                sh 'docker rm myapp-container || true'
                sh 'docker run -d -p 80:5000 --name myapp-container myapp'
            }
        }
    }
}
