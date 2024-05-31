pipeline {
    agent {
        label 'dev'
    }

    stages {
        stage('GitCheck') {
            steps {
                sh "git --version"
				sh "whoami"
				sh "python --version"
            }
        }
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SainiAnmol/testing.git']])
            }
        }
        stage('Build') {
            steps {
                sh "sudo python test.py"
            }
        }
        stage('Success') {
            steps {
                echo "Successful!!"
            }
        }
    }
}
