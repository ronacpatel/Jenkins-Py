pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ronacpatel/Jenkins-Py']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/ronacpatel/Jenkins-Py'
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
    }
}
