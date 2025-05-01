pipeline {
    agent { label 'python-agent' }

        stage('Verify Python') {
            steps {
                sh 'which python3'
                sh 'python3 --version'
            }
        }

        stage('Install') {
            steps {
                sh 'python3 -m pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'pytest --html=report.html || true'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'report.html', fingerprint: true
        }
    }
}
