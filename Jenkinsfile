pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git 'https://github.com/<yourusername>/demoapp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t demoapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 demoapp'
            }
        }
    }
}
