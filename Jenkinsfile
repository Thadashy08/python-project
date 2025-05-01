pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                sh 'python3 -m pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
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
