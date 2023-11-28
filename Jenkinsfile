pipeline {
    agent {
      label 'Node2'
    }
    environment {
	APP_BUILD_NUBER = '1.0.0'
	DOCKERHUB_CREDENTIALS = credentials('manngo2013-dockerhub')
    }
	
    stages {
        stage('Build Docker Image') {
            steps {
                sh "docker build -t manngo2013/static-web:${env.APP_BUILD_NUBER} ."
            }
        }
	stage('Login DockerHUB') {
            steps {
                sh "echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin"
            }
        }
	stage('Push DockerHUB') {
            steps {
                sh "docker push manngo2013/static-web:${env.APP_BUILD_NUBER}"
            }
        }
    }
	post {
		always {
			sh 'docker logout'
		}
	}
}
