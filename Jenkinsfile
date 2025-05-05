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
}

post {
    always {
        echo  'this section run always'
    }
    success {
        echo  'this scection run when pipline sucess'
    }
    failure {
        echo  'this section run when pipeline fail'
    }
}