pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build --no-cache -t prakash-devops .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker stop website || true'
                sh 'docker rm website || true'
                sh 'docker run -d -p 80:80 --name website prakash-devops'
            }
        }
    }
}
