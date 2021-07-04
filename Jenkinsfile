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