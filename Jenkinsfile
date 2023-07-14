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
            agent {
                node{
                    label "DockerServer";
                }
            }
            steps {
                sh 'docker build https://github.com/Mficius/test_jenkins.git -t test_jenkins:latest'
            }
        }

        stage('Deploy')  {
            agent {
                node{
                    label "DockerServer";
                }
            }
            steps {
                sh 'docker run -tdi -p 5000:5000 test_jenkins:latest'
            }
        }
            
    }
     
}