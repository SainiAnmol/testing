pipeline {
    agent any

    stages {
        stage('GitCheck') {
            steps {
                sh "git --version"
            }
        }
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
