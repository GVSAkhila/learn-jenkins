pipeline {
    agent {
        label 'AGENT-1'
    }

    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

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
            when {
               expression { env.GIT_BRANCH = "origin/main" }
            }
            steps {
                sh 'echo Deployed'
            }
        }

        stage('Print Params') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"  // Consider masking in real use
            }
        }

     stage('Approval'){
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
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
