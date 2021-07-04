pipeline {
    agent any
    environment {
        TESTCRED = credentials('test-cred-01')
        }
    stages {
        stage('Build') {
            steps {
                sh '''
                    chmod +x test.sh
                    ./test.sh
                '''
            }
        }
        stage('Sanity check') {
            steps {
                input "Does the staging environment look ok?"
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    echo "its a yes"
                '''
            }
        }
    }
    post {
        always {
            sh 'echo test'
        }
        failure {
            sh 'echo fail'
        }
    }
}