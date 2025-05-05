pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 10, unit: 'SEC')
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo Building'
                sh 'sleep 10'
            }
        }
        stage('Testing') {
            steps {
                sh 'echo Testing'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo Deployed'
                
            }
        }
    }

    post {
        always {
            echo 'This section runs always'
            deleteDir()
        }
        success {
            echo 'This section runs when the pipeline succeeds'
        }
        failure {
            echo 'This section runs when the pipeline fails'
        }
    }
}
