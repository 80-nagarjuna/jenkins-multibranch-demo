pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Build') {
            steps {
                echo "Running on branch: ${env.BRANCH_NAME}"
                sh 'hostname'
                sh 'whoami'
                sh 'pwd'
            }
        }
    }
}