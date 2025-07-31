pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'git@github.com:devopss-dev/my-staticapp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-staticapp:latest .'
            }
        }

        stage('Deploy to Docker Swarm') {
            steps {
                sh 'docker stack deploy -c docker-compose.yml mystaticstack'
            }
        }
    }
}

