pipeline {
    agent { label 'python-agent' }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Thadashy08/python-project.git'
            }
        }

        stage('Verify Python') {
            steps {
                sh 'which python3'
                sh 'python3 --version'
            }
        }

        stage('Install') {
            steps {
                sh 'python3 -m pip install --upgrade pip --break-system-packages'
                sh 'pip install -r requierements.txt --break-system-packages'
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
