pipeline {
    agent any;
    stages {
        stage('Preparing the environment') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }
        stage('Code Quality') {
            steps {
                sh 'python3 -m pylint app.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }

        stage('Build') {
            steps {
                sh 'exit 1'
            }
        }

        stage('Delivery') {
            steps {
                sh 'exit 1'
            }
        }

        stage('Deploy')  {
            steps {
                sh 'exit 1'
            }
        }
            
    }
     
}