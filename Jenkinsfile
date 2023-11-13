pipeline {
    agent any
    environment  {
        name = 'yash'
    }
    parameters {
        string(name: 'person', defaultValue: 'yash shetty', description: 'who are you?')
        booleanParam(name: 'Male', defaultValue: true, description: "")
        choice(name: 'City', choices: ['M','K','B','A'], description: "")
    }
    stages {
        stage('run a command') {
            steps {
                sh '''
                ls
                pwd
                touch cats
                ls
                '''
            }
        }
         stage('Environment Variables') {
             environment {
                 username = 'shailu'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "should we connect?"
                ok "yes we should"
            }
            steps {
                echo 'Hello World'
            }
        }
         stage('deploy on prod') {
            steps {
                echo 'Hello World'
            }
        }
    }
    post{
        always {
            echo 'i will always say hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Success'
        }
    }
}
