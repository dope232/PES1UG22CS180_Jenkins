pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/main']], 
                userRemoteConfigs: [[url: 'https://github.com/dope232/PES1UG22CS180_Jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS180-1'
                sh 'g++ main/main.cpp -o output' 
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy' 
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
