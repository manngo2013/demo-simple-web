pipeline {
    agent {
      label 'Node2'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                sh "docker build -t static-web ."
            }
        }
    }
}
