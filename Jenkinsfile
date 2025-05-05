pipeline {
    agent {
        label 'AGENT-1'
    }
   options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds()
    }

    parameters  {
     string(name: 'ENV', defaultValue: 'dev', description: 'Enter the environment name')
     booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests?')
     choice(name: 'DEPLOY_REGION', choices: ['us-east-1', 'eu-west-1', 'ap-south-1'], description: 'Select AWS region')
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo Building'
                //sh 'sleep 10'
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
    stages {
        stage('Print Params') {
            steps {
                echo "Environment: ${params.ENV}"
                echo "Run Tests: ${params.RUN_TESTS}"
                echo "Deploy Region: ${params.DEPLOY_REGION}"
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
