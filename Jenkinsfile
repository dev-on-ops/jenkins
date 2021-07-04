pipeline {
    agent any
    environment {
        TESTCRED = credentials('test-cred-01')
        }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh 'echo $TESTCRED'
                sh 'echo $TESTCRED > /tmp/testcredfile'
                sh 'cat /tmp/testcredfile'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}