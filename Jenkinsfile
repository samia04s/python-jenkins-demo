pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                git 'https://github.com/samia04s/python-jenkins-demo'
            }
        }

        stage('Build Docker image') {
            steps {
                script {
                    dockerImage = docker.build("python-jenkins-demo")
                }
            }
        }

        stage('Run tests inside container') {
            steps {
                script {
                    dockerImage.inside {
                        sh 'pytest'
                    }
                }
            }
        }
    }
}
