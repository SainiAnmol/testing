pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SainiAnmol/testing.git']])
            }
        }
        stage('Build') {
            steps {
                sh "python test.py"
            }
        }
        stage('Success') {
            steps {
                echo "Successful!!"
            }
        }
    }
}
