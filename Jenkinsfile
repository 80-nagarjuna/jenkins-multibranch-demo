pipeline {
    agent {
        label 'linux'
    }

    stages {

        stage('Checkout Info') {
            steps {
                echo "Build Information"
                echo "Job Name     : ${env.JOB_NAME}"
                echo "Build Number : ${env.BUILD_NUMBER}"
                echo "Branch       : ${env.BRANCH_NAME}"
                echo "Workspace    : ${env.WORKSPACE}"
            }
        }

        stage('Build') {
            steps {
                echo "Running build..."

                sh 'hostname'
                sh 'whoami'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Verify HTML') {
            steps {
                sh '''
                if [ -f index.html ]; then
                    echo "index.html found."
                else
                    echo "index.html not found!"
                    exit 1
                fi
                '''
            }
        }

        stage('Validate HTML') {
            steps {
                sh '''
                echo "File Information"
                wc -l index.html
                wc -c index.html
                head -5 index.html
                '''
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully."
        }

        failure {
            echo "Pipeline failed."
        }

        always {
            echo "Build finished."
        }
    }
}