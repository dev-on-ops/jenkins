pipeline {
    agent any
    environment {
        TESTCRED = credentials('test-cred-01')
        }
    stages {
        stage('Build') {
            steps {
                sh '''
                    echo "#!/bin/bash
                    exit 1" >> /tmp/test.sh
                    chmod +x /tmp/test.sh
                    /tmp/test.sh
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