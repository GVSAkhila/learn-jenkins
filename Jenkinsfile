pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                sh 'echo Building'
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
        }
        success {
            echo 'This section runs when the pipeline succeeds'
        }
        failure {
            echo 'This section runs when the pipeline fails'
        }
    }
}
