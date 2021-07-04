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
                sh 'echo "The secret value is: $TESTCRED" > /tmp/file'
                sh 'cat /tmp/file'
                sh 'cp /tmp/file /tmp/file1'
                sh 'cat /tmp/file1'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}