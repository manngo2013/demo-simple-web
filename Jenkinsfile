pipeline {
    agent {
      label 'Node2'
    }
    environment {
		APP_BUILD_NUBER = '1.0.0'
	}
	
    stages {
        stage('Build Docker Image') {
            steps {
                sh "docker build -t static-web:${env.APP_BUILD_NUBER} ."
            }
        }
    }
}
