pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Thadashy08/python-project.git'
            }
        }
        stage('Install') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest --html=report.html'
            }
        }
    }
}
