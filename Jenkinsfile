pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t demoapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop demoapp_container || true
                docker rm demoapp_container || true
                docker run -d --name demoapp_container -p 8081:80 demoapp
                '''
            }
        }
    }
}
