pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                git 'https://github.com/samia04s/python-jenkins-demo'
            }
        }

        stage('Install dependencies and run tests') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    pytest
                '''
            }
        }
    }
}
