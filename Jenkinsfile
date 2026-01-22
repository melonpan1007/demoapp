pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t demoapp .'
            }
        }

        stage('Run Container') {
            steps {
                bat '''
                docker stop demoapp_container || exit 0
                docker rm demoapp_container || exit 0
                docker run -d --name demoapp_container -p 8081:80 demoapp
                '''
            }
        }
    }
}
