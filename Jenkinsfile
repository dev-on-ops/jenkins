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
                sh '''
                    chmod +x script1.sh
                    ./script1.sh
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    echo "its worked"
                '''
            }
        }
    }
    post {
        always {
            sh 'echo "Done"'
        }
        failure {
            sh 'echo "fail"'
        }
    }
}