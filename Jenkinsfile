pipeline {
    agent {
        docker {
            image 'python:3.10'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Thadashy08/python-project.git'
            }
        }
        stage('Install') {
            steps {
                sh 'pip install --upgrade pip'
                sh 'pip install -r requierements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest --html=report.html'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'report.html', fingerprint: true
        }
    }
}
